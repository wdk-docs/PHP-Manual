MongoGridFSFile类
=================================

(PECL mongo >=0.9.0)

介绍
-------

A database file object.

类简介
-----------

.. code-block:: php

 <?PHP
 MongoGridFSFile {
  /* Fields */
  public array $file = NULL ;
  protected MongoGridFS $gridfs = NULL ;
  /* Methods */
  public MongoGridfsFile::__construct ( MongoGridFS $gridfs , array $file )
  public string getBytes ( void )
  public string getFilename ( void )
  public stream getResource ( void )
  public int getSize ( void )
  public int write ([ string $filename = NULL ] )
 }
 ?>
