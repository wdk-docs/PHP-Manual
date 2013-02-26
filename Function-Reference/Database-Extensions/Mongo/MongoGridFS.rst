MongoGridFS类
==============



(PECL mongo >=0.9.0)

介绍
--------------------

Utilities for storing and retrieving files from the database.

GridFS is a storage specification all supported drivers implement. Basically, it defines two collections: files, for file metadata, and chunks, for file content. If the file is large, it will automatically be split into smaller chunks and each chunk will be saved as a document in the chunks collection.

Each document in the files collection contains the filename, upload date, and md5 hash. It also contains a unique _id field, which can be used to query the chunks collection for the file's content. Each document in the chunks collection contains a chunk of binary data, a files_id field that matches its file's _id, and the position of this chunk in the overall file.

For example, the files document is something like:

<?php
array("_id" => 123456789, "filename" => "foo.txt", "chunkSize" => 3, "length" => 12);
?>
and the chunks documents look like:
<?php
array("files_id" => 123456789, "n" => 0, "data" => new MongoBinData("abc"));
array("files_id" => 123456789, "n" => 1, "data" => new MongoBinData("def"));
array("files_id" => 123456789, "n" => 2, "data" => new MongoBinData("ghi"));
array("files_id" => 123456789, "n" => 3, "data" => new MongoBinData("jkl"));
?>
Of course, the default chunk size is thousands of bytes, but that makes an unwieldy example.

跨语言的兼容性
--------------------

You should be able to use any files created by MongoGridFS with any other drivers, and vice versa. However, some drivers expect that all metadata associated with a file be in a "metadata" field. If you're going to be using other languages, it's a good idea to wrap info you might want them to see in a "metadata" field. For example, instead of:

<?php

$grid->storeFile("somefile.txt", array("date" => new MongoDate()));

?>
use something like:

<?php

$grid->storeFile("somefile.txt", array("metadata" => array("date" => new MongoDate())));

?>

MongoGridFS家庭
--------------------------

MongoGridFS represents the files and chunks collections. MongoGridFS extends MongoCollection, and an instance of MongoGridFS has access to all of MongoCollection methods, which act on the files collection:

<?php

$grid = $db->getGridFS();
$grid->update(array("filename" => "foo"), $newObj); // update on the files collection

?>
Another example of manipulating metadata:

<?php

// save a file
$id = $grid->storeFile("game.tgz");
$game = $grid->findOne();

// add a downloads counter
$game->file['downloads'] = 0;
$grid->save($game->file);

// increment the counter
$grid->update(array("_id" => $id), array('$inc' => array("downloads" => 1)));

?>
You can also access the chunks collection from an instance of MongoGridFS:

<?php

  $chunks = $grid->chunks; // $chunks is a normal MongoCollection
$chunks->insert(array("x" => 4));

?>
There are some methods for MongoGridFS with the same name as MongoCollection methods, that behave slightly differently. For example, MongoGridFS::remove() will remove any objects that match the criteria from the files collection and their content from the chunks collection.

To store something new in GridFS, there are a couple options. If you have a filename, you can say:

<?php

$grid->storeFile($filename, array("whatever" => "metadata", "you" => "want"));

?>
If you have a string of bytes that isn't a file, you can also store that using MongoGridFS::storeBytes():

<?php

$grid->storeBytes($bytes, array("whatever" => "metadata", "you" => "want"));

?>
Querying a MongoGridFS collection returns a MongoGridFSCursor, which behaves like a normal MongoCursor except that it returns MongoGridFSFiles instead of associative arrays.

MongoGridFSFiles can be written back to disc using MongoGridFSFile::write() or retrieved in memory using MongoGridFSFile::getBytes(). There is currently no method that automatically streams chunks, but it would be fairly easy to write by querying the $grid->chunks collection.

MongoGridFSFile objects contain a field file which contains any file metadata.

类简介
--------------------

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

参见
------------------

MongoDB core docs on » GridFS
LightCube Solutions blog post on » saving user uploads
LightCube Solutions blog post on » adding metadata to files
