MongoGridFS类
==============



(PECL mongo >=0.9.0)

介绍
--------------------

Utilities for storing and retrieving files from the database.

GridFS is a storage specification all supported drivers implement. Basically, it defines two collections: files, for file metadata, and chunks, for file content. If the file is large, it will automatically be split into smaller chunks and each chunk will be saved as a document in the chunks collection.

Each document in the files collection contains the filename, upload date, and md5 hash. It also contains a unique _id field, which can be used to query the chunks collection for the file's content. Each document in the chunks collection contains a chunk of binary data, a files_id field that matches its file's _id, and the position of this chunk in the overall file.

例如, 文件文档如下:

.. code-block:: php

 <?php
   array("_id" => 123456789, "filename" => "foo.txt", "chunkSize" => 3, "length" => 12);
 ?>

块文件如下:

.. code-block:: php

 <?php
  array("files_id" => 123456789, "n" => 0, "data" => new MongoBinData("abc"));
  array("files_id" => 123456789, "n" => 1, "data" => new MongoBinData("def"));
  array("files_id" => 123456789, "n" => 2, "data" => new MongoBinData("ghi"));
  array("files_id" => 123456789, "n" => 3, "data" => new MongoBinData("jkl"));
 ?>

当然, 默认块大小是千字节, but that makes an unwieldy example.

跨语言兼容
--------------------

You should be able to use any files created by MongoGridFS with any other drivers, and vice versa. However, some drivers expect that all metadata associated with a file be in a "metadata" field. If you're going to be using other languages, it's a good idea to wrap info you might want them to see in a "metadata" field. For example, instead of:

.. code-block:: php
 <?php
  $grid->storeFile("somefile.txt", array("date" => new MongoDate()));
 ?>

use something like:

.. code-block:: php

 <?php
  $grid->storeFile("somefile.txt", array("metadata" => array("date" => new MongoDate())));
 ?>

MongoGridFS家庭
--------------------------

MongoGridFS represents the files and chunks collections. MongoGridFS extends MongoCollection, and an instance of MongoGridFS has access to all of MongoCollection methods, which act on the files collection:

.. code-block:: php

 <?php
  $grid = $db->getGridFS();
  $grid->update(array("filename" => "foo"), $newObj); // update on the files collection
 ?>

另一个操作元数据实例:

.. code-block:: php

 <?php
  // 保存文件
  $id = $grid->storeFile("game.tgz");
  $game = $grid->findOne();
  // 添加一个下载计数器
  $game->file['downloads'] = 0;
  $grid->save($game->file);
  // 累加计数器
  $grid->update(array("_id" => $id), array('$inc' => array("downloads" => 1)));
 ?>

你也可以从MongoGridFS实例访问块集合:

.. code-block:: php

 <?php
  $chunks = $grid->chunks; // $chunks is a normal MongoCollection
  $chunks->insert(array("x" => 4));
 ?>

There are some methods for MongoGridFS with the same name as MongoCollection methods, that behave slightly differently. For example, MongoGridFS::remove() will remove any objects that match the criteria from the files collection and their content from the chunks collection.

To store something new in GridFS, there are a couple options. If you have a filename, you can say:

.. code-block:: php

 <?php
  $grid->storeFile($filename, array("whatever" => "metadata", "you" => "want"));
 ?>

If you have a string of bytes that isn't a file, you can also store that using MongoGridFS::storeBytes():

.. code-block:: php

 <?php
  $grid->storeBytes($bytes, array("whatever" => "metadata", "you" => "want"));
 ?>
 
Querying a MongoGridFS collection returns a MongoGridFSCursor, which behaves like a normal MongoCursor except that it returns MongoGridFSFiles instead of associative arrays.

MongoGridFSFiles can be written back to disc using MongoGridFSFile::write() or retrieved in memory using MongoGridFSFile::getBytes(). There is currently no method that automatically streams chunks, but it would be fairly easy to write by querying the $grid->chunks collection.

MongoGridFSFile objects contain a field file which contains any file metadata.

类简介
--------------------

.. code-block:: php

 <?PHP
 extends MongoCollection {
  /* Fields */
  public MongoCollection $chunks = NULL ;
  protected string $filesName = NULL ;
  protected string $chunksName = NULL ;
  /* Methods */
  public __construct ( MongoDB $db [, string $prefix = "fs" [, mixed $chunks = "fs" ]] )
  public bool delete ( mixed $id )
  public array drop ( void )
  public MongoGridFSCursor find ([ array $query = array() [, array $fields = array() ]] )
  public MongoGridFSFile findOne ([ mixed $query = array() [, mixed $fields = array() ]] )
  public MongoGridFSFile get ( mixed $id )
  public mixed put ( string $filename [, array $metadata = array() ] )
  public bool remove ([ array $criteria = array() [, array $options = array() ]] )
  public mixed storeBytes ( string $bytes [, array $metadata = array() [, array $options = array() ]] )
  public mixed storeFile ( string $filename [, array $metadata = array() [, array $options = array() ]] )
  public mixed storeUpload ( string $name [, array $metadata ] )
 }
 ?>

参见
------------------

MongoDB 核心文档 » `GridFS <http://docs.mongodb.org/manual/applications/gridfs/>`

LightCube Solutions blog post on » :ref:`saving-user-uploads`

LightCube Solutions blog post on » :ref:`adding-metadata-tofiles`
