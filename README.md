# Vincentius Sagi Alban Anindyajati
=====
# **Creating, Importing, Querying, and Exporting Data with Amazon DynamoDB**

## **DynamoDB**
Amazon DynamoDB is an extensively supervised NoSQL database service accessible through Amazon Web Services (AWS). NoSQL database management solutions deviate from the conventional relational database model. DynamoDB is ideal for applications that prioritize fast and reliable performance, especially when dealing with large amounts of data. It offers reduced response times, high availability, and effortless scalability. By distributing data across multiple servers, DynamoDB ensures consistent performance even as data and traffic volumes grow. Storage is facilitated by SSDs, which provide read and write operations with extremely low latency in the range of milliseconds.<br>
<br>
DynamoDB's schema-less data model eliminates the need for rigid table structures and predefined schemas. Instead, it adopts a key-value store approach, organizing data into tables and items. This flexibility enables agile development and seamless adjustment to evolving data needs. Moreover, DynamoDB offers automated data replication and multi-region capabilities, guaranteeing high availability and durability..

## **Create a Table in DynamoDB**
First, we search for "DynamoDB" in the AWS service menu. <br>
<br>
![image] (https://github.com/vincentiussagi/bdcc/blob/a7250020b9c5d60b89f18c7bb47126373f7519a8/1.png)) <br>
<br>

Then, to create a table, click "Create table". <br>
<br>
![image]() <br>
<br>

After that, a menu will display with options for configuring the table. Fill in the table name, partition key, and sort key (optional) in the table details. <br>
<br>
![image]() <br>
<br>

Actually, users can alter the table's features, such as the capacity calculator and table class. I simply use the default parameters for this task.Click "Create Table" once all the settings have been made. <br>
<br>
![image]() <br>
<br>

Following creation, the table will appear in the DynamoDB tables list. Wait a short while for the status table to change to active if it is initially still developing.<br>
<br>
![image]() <br>
<br>

Go to Explore items: your-table-name, select "Create item," enter the value for the table attribute, and then select "Create item" to add data to the table.<br>
<br>
![image]() <br>
<br>

You can also add new attributes by clicking "Add new attribute" in the upper right corner of the image above, keeping in mind the data type.<br>
<br>
![image]()<br>
<br>

## **Import Data**
Simply select DynamoDB from the menu, click Import from S3, and then select "Import from S3" to import datasets from an S3 bucket. <br>
<br>
![image]() <br>
<br>

You can upload your files to the S3 bucket if you haven't already. In this case, I only need to navigate to the S3 directory since I have uploaded my files to S3. After that click "browse" to find the directory for the file to upload. <br>
<br>
![image]() <br>
<br>

Ensure that your file format matches your file format in the "Import file format" field. In this instance, I'm uploading from a csv file, so I click "Next" after selecting csv as the file format. <br>
<br>
<img width="608" alt="image" src=""> <br>
<br>

Then, fill out the table details. For the partition keys, choose the column that has the data's unique value. And then just click next, next, and import.<br>
<br>
<img width="408" alt="image" src="">
<br>

Simply wait for the import status to be finished. The quantity of datasets determines the import time. <br>
<br>
![image]() <br>
<br>

You can go back and browse items to see your newly imported datasets when the dataset has been fully loaded. And the image below shows how my dataset appears.<br>
<br>
<img width="607" alt="image" src=""><br>
<br>

## **Scan Data**
Scanning and searching for data can help you uncover information more quickly. Let's try running a values ​​scan on the data first. I selected "scan" then "table to scan" and "attributes to project filter" because I was looking for Sales ($). You can quickly search using filters by filtering the value. in this case, I'm looking for the attribute "Sales ($)" when the value is "greater than or equal to 10.4". After that click "run". <br>
<br>
![image]()<br>
<br>

Here is the outcome of my scanning, indicating that there are 194 rows of Advertising budget and sales with the Sales ($) when the value is greater than or equal to 10.4. <br>
<br>
<img width="602" alt="image" src=""><br>
<br>

## **Querying Data**
In fact, dynamo database queries are very sophisticated, thus for the purposes of this experiment, I only employ queries that search for data using unique keys. Let's try searching for unique data. <br>
<br>
![image]()<br>
<br>

You can choose query and then enter the partition key from your data in "ID" as a partition key. In this case, I'm using "79" to search for things with partition keys equal to 79, and the outcome is shown in the image below. <br>
<br>
<img width="598" alt="image" src=""><br>
<br>

## **Export Data**
Your table can be exported and stored on S3. Your first step should be to select "Export to S3" from the Dynamo DB menu. <br>
<br>
![image]() <br>
<br>

<!-- Then, a display of the export details will appear. You must fill out the source table you want to import and the S3 bucket's destination. In this case, i've used the default settings for additional options. After that, click Export. <br> -->
<br>
![image]() <br>
<br>

Simply wait for the export table status to be completed. Once it is, the display will look like the one in the previous image. <br>
<br>
![image]()<br>
<br>

After that, let's check to the AWS bucket <br>
<br>
![image]()<br>
<br>

As can be observed, exporting data from DynamoDB has resulted in the appearance of a new folder with the name "AWSDynamoDB/.". Therefore, the export is finished.
<br>

## **Conclusion**
Amazon DynamoDB is a highly scalable and high-performance NoSQL database service. With a key-value storage model, DynamoDB provides low response times and high throughput. DynamoDB is also flexible in terms of data schemas, allowing arbitrary data storage. With high durability and fault tolerance, DynamoDB maintains high data availability. Overall, DynamoDB is a powerful NoSQL solution for managing large-scale data with fast performance and easy management. With DynamoDB, you can construct tables, import datasets, and run queries or scans to get the information you need.
















