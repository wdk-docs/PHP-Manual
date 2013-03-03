MongoGridFSCursor类
===========================

(PECL mongo >=0.9.0)

介绍
------------

Cursor for database file results.

类简介
-----------

.. code-block:: php

 <?PHP
   extends MongoCursor {
    /* Fields */
    protected MongoGridFS $gridfs = NULL ;
    /* Methods */
    public __construct ( MongoGridFS $gridfs , resource $connection , string $ns , array $query , array $fields )
    public MongoGridFSFile current ( void )
    public MongoGridFSFile getNext ( void )
   public string key ( void )
  }
 ?>
