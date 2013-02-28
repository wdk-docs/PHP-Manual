.. _adding-metadata-tofiles:

在MongoDB/PHP里添加元数据到文件里
====================================

`文件源`_

.. _文件源: http://www.lightcubesolutions.com/blog/?p=228

As a quick followup to the last blog, I was asked to demonstrate how we could include some metadata with a file during or after upload.

This is a great feature since we can retrieve all the information attached with a document during a query. Including metadata (i.e. comments, dates, votes or WHATEVER ELSE YOU LIKE) is just as easy.

We are going to pick up the ball at the point where you’ve got all your MongoDB objects ready:

.. code-block:: php

 <?php
  $date = new MongoDate();  
  //使用 $set 添加元数据到文件  
  $metaData = array('$set' => array(“comment”=>”MongoDB is awesome”, “date”=>$date));  
  //设置搜索条件 
  $criteria = array('_id' => $id);  
  //更新文件的一些信息  
  $db->grid->update($criteria, $metaData);  
 ?>

Did you break a sweat? Probably not.

BTW, I threw in a little extra tidbit there with MongoDate(). It’s a better way of inputting a date into Mongo instead of using PHP date with a bunch of formatting to get it just right.


