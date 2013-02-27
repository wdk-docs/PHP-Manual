.. _saving-user-uploads:

MongoDB和PHP – GridFS快速浏览
================================

源文件： `a link`_.

.. _a link: http://www.lightcubesolutions.com/blog/?p=209

I’ve been tweeting quite a bit about MongoDB over the past few weeks and its time to blog.

About 2 months ago we decided to install and mess around with MongoDB. We went from messing around to serious adoption about 2 weeks ago when we realized the power of working with it and PHP. It was Mitch Pirtle of www.spacemonkeylabs.com that first pointed us in this direction. Mitch was very enthusiastic about Mongo as he explained the great potential. Yet, it was only until I added an array of data from PHP into Mongo that my eyes started to open up.

Go ahead, open another tab in your browser (KEEPING THIS ONE OPEN) and Google MongoDB if you haven’t already (I made it easy providing the link). You’ll find sufficient documentation to give you the warm and fuzzy that 10gen isn’t messing around. They are in the database game for the long haul.

During our play with MongoDB we realized how true the term NoSQL is. For all you SQL grease monkeys out there it’s liberating. No Joins, No Select, just plain NoSQL.

As an example, let’s start off with putting uploaded files “directly” into MongoDB via GridFS (the storage specification for handling large files). Here is how simple it is:

First, we are going to assume you already have the code in place to handle the upload itself. We first tested this using SWFUpload which provides quite a bit of flexibility if you like to control how your page looks during upload. From a PHP perspective, the uploaded file will be accessible via the predefined variable $_FILES.

这些是你上传文件到MongoDB必须做的:

.. code-block:: php

 <?php  
  $m = new Mongo(); //connect  
  $db = $m->selectDB("example"); //选择Mongo库
  $grid = $db->getGridFS(); //使用GridFS类来操作文件  
  $name = $_FILES['Filedata']['name']; //可选择的 - 抓取上传文件名  
  $id = $grid->storeUpload('Filedata',$name) //载入文件到MongoDB  
 ?>

Yep, that was it. One thing that took me a “second” to realize is that you actually pass the literal name of the file_post_name (in the example ‘Filedata’) to MongoDB. It does all the heavy lifting of getting the data from the system and storing it. Also, take note that you get an $id back which is the MongoID that acts as the “primary key”. That makes it easy for you to reference the file right away if you need to.

So that’s a rather quick look and tip for MongoDB. Stay tuned  as we continue to put out our MongoDB tricks and tips for PHP. We’re in it for the long haul too.


