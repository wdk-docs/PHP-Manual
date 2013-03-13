写关注
===============

MongoDB provides several different ways of selecting how durable a write to the database should be. These ways are called Write Concerns and span everything from completely ignoring all errors, to specifically targetting which servers are required to confirm the write before returning the operation.

When a write (such as with MongoCollection::insert(), MongoCollection::update(), and MongoCollection::remove()) is given a Write Concern option ("w") the driver will send the query to MongoDB and then followup with a getLastError command (GLE) with the Write Concern option which will be blocked until the Write Concern condition is verified to be fullfilled, or the query times out (controlled with the "wtimeout" option, no timeout by default).

.. Warning:: Even though a getLastError command times out the data will most likely have been written to the primary server and will be replicated to all the secondaries once they have cought up.

The typical reasons for a timeout to happen is if you specify a Write Concern which requires confirmation from more servers then you currently have available.

When using acknowledged writes and the replica set has failed over, the driver will automatically disconnect from the primary, throw an exception, and attempt to find a new primary on the next operation (your application must decide whether or not to retry the operation on the new primary).

When using unacknowledged writes (w=0) and the replica set has failed over, there will be no way for the driver to know about the change so it will continue and silently fail to write.

The default Write Concern for the MongoClient is 1: acknowledge write operations.

Available Write Concerns

=========== ================================ ==============================================================================================
Write       Concern                          Meaning Description
=========== ================================ ==============================================================================================
w=0         Unacknowledged                   A write will not be followed up with a GLE call, and therefore not checked ("fire and forget")
w=1         Acknowledged                     The write will be acknowledged by the server (the primary on replica set configuration)
w=N         Replica Set Acknowledged         The write will be acknowledged by the primary server, and replicated to N-1 secondaries.
w=majority  Majority Acknowledged            The write will be acknowledged by the majority of the replica set (including the primary). This is a special reserved string.
w=<tag set> Replica Set Tag Set Acknowledged The write will be acknowledged by members of the entire tag set
j=true      Journaled                        The write will be acknowledged by primary and the journal flushed to disk
=========== ================================ ==============================================================================================

Unacknowledged Writes
---------------------

By not requiring the server to acknowledge writes the writes can be performed extremely quickly, but you don't know whether or not they actually succeeded. Writes can fail for a number of reasons: if there are network problems, if a database server goes down, or if the write was simply invalid (e.g., writing to a system collection; or duplicate key errors).

While developing, you should always use acknowledged writes (to protect against inadvertent mistakes, such as syntax errors, invalid operators, duplicate key errors and so on). In production, unacknowledged writes can be used for "unimportant" data. Unimportant data varies on application, but it's generally automatically (instead of user generated) data, such as click tracking or GPS locations, where you can get thousands of records per second.

It is strongly recommended that you do an acknowledged write at the end of series of unacknowledged writes. Doing so will not incur in a too large performance penalty, but still allow you to catch any errors that may have occurred.

Example #1 Unacknowledged WriteConcern, followed with Acknowledged Write

.. code-block:: php

 <?php
   $collection->insert($someDoc, array("w" => 0));
   $collection->update($criteria, $newObj, array("w" => 0));
   $collection->insert($somethingElse, array("w" => 0));
   try {
       $collection->remove($something, array("w" => 1));
   } catch(MongoCursorException $e) {
       /* Handle the exception.. */
       /* Here we should issue find() queries on the IDs generated for
       $somethingElse and $someDoc to verify they got written to the database and
       attempt to figureout where in the chain something happened. */
   }
 ?>

If the last write throws an exception, you know that there's a problem with your database.
Acknowledged Writes

These type of write operations will make sure that the database has accepted the write operation before returning success. If the write failed, it will throw a MongoCursorException with an explanation of the failure. The MongoClient default behaviour is to acknowledge the write (w=1).

It is possible to specify how many members of an replica set have to acknowledge the write (i.e. have it replicated) before the write is deemed acknowledged and the operation returns.

Example #2 Acknowledged Writes

.. code-block:: php

 <?php
   // Force acknowledgement from the primary only
   $collection->insert($doc, array("w" => 1));

   // Force acknowledgement from the primary, and one other member of the
   // replica set
   $collection->insert($doc, array("w" => 2));

   // Force acknowledgement from the primary, and six other members of the
   // replica set (you probably never should do this):
   $collection->insert($doc, array("w" => 7));

Keep in mind to select your Write Concern carefully. If you have a replica set with 5 members, and you select Write Concern of 4 you will risk the write blocking forever when one member of the replica set goes down for maintenance or a temporary network outage happens.
Warning
Passing in a string value for Write Concern has a specific meaning (Replica Set Tag Set Acknowledged). Please be careful of NOT using string values for numbers (i.e. array("w" => "1")) as it will be treated as a tag set name.

Majority Acknowledged Writes
---------------------------------

Using the special majority Write Concern option is the recommended way for writes that are required to survive the apocalypse, as it will ensure the majority of your replica set will have the write and will therefore be guaranteed to survive all usual suspect outage scenarios.

Example #3 Majority Acknowledged Write

.. code-block:: php

 <?php
   $collection->insert($someDoc, array("w" => "majority"));
 ?>

Journaled Writes
------------------

When connecting to a replica set the default Write Concern is only to have the primary server acknowledge the write. There is however a 100ms window until the write gets journaled and flushed to disk. It is possible to force the write to be journaled before acknowledging the write by setting the j option:

Example #4 Acknowledged and Journaled Write
Forcing journal flush

.. code-block:: php

 <?php
   $options = array(
    "w" => 1,
    "j" => true,
 );
 try {
    $collection->insert($document, $options);
 } catch(MongoCursorException $e) {
    /* handle the exception */
 }

.. seealso:: » MongoDB WriteConcern docs

更新日志
--------------

===== =============================================================================================================================
版本  说明
===== =============================================================================================================================
1.3.0 MongoClient was introduced and defaults to acknowledged writes. The deprecated Mongo defaults to unacknowledged writes.
1.3.0 The "safe" write option has been deprecated and is not available with the new MongoClient class. Use the "w" option instead.
===== =============================================================================================================================
