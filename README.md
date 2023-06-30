# Vincentius Sagi Alban Anindyajati
=====
# **Creating, Importing, Querying, and Exporting Data with Amazon DynamoDB**

## **DynamoDB**
Amazon DynamoDB is an extensively supervised NoSQL database service accessible through Amazon Web Services (AWS). NoSQL database management solutions deviate from the conventional relational database model. DynamoDB is ideal for applications that prioritize fast and reliable performance, especially when dealing with large amounts of data. It offers reduced response times, high availability, and effortless scalability. By distributing data across multiple servers, DynamoDB ensures consistent performance even as data and traffic volumes grow. Storage is facilitated by SSDs, which provide read and write operations with extremely low latency in the range of milliseconds.<br>
<br>
DynamoDB's schema-less data model eliminates the need for rigid table structures and predefined schemas. Instead, it adopts a key-value store approach, organizing data into tables and items. This flexibility enables agile development and seamless adjustment to evolving data needs. Moreover, DynamoDB offers automated data replication and multi-region capabilities, guaranteeing high availability and durability..

## **Creating a Table in DynamoDB**
First, we search for "DynamoDB" in the AWS service menu. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/1.png?raw=true)<br>
<br>

Click "Tables" on the menu on the left side <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/2.png?raw=true)<br>
<br>

Then click on "Create table". <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/3.png?raw=true)<br>
<br>

Then a table details window menu will pop-up. Fill in the table name, partition key, and sort key (optional) in the table details. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/4.png?raw=true)<br>
<br>

Now it will show a menu where the user can alter the table's features, such as the capacity calculator and table class. We'll simply use the default parameters for this task. Click "Create Table" once all the settings have been made. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/5.png?raw=true) <br>
<br>

Following creation, the table will appear in the DynamoDB tables list. Wait a minute or two until the status change to active if it is initially still developing.<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/6.png?raw=true) <br>
<br>

Next, Go to Explore items: <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/7.png?raw=true) <br>
<br>
Select [your-table-name] -> select "Create item", <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/8.png?raw=true) <br>
<br>
Enter the value for the table attribute, and then select "Create item" to add data to the table. You can also add new attributes by clicking "Add new attribute" in the upper right corner, keeping in mind the data typr<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/9.png?raw=true) <br>
<br>

Now we check the items returned<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/10.png?raw=true) <br>
<br>

## **Importing Data in DynamoDB**
On the DynamoDB services menu, Click "Import From S3" on the menu on the left side <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/11.png?raw=true) <br>
<br>

Then select "Import from S3" to import datasets from an S3 bucket. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/12.png?raw=true) <br>
<br>

As the menu says, it is importing from S3 Buckets, so you might want to make sure you already uploaded the data there. If done click "browse" and find the directory for the file to upload. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/13.png?raw=true) <br>
<br>

Because I use a csv file, so I choose 'CSV' as the import file format. Next, make sure about the csv header and delimiter. If done, click next. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/14.png?raw=true)  <br>
<br>

Then, fill out the table details. For the partition keys, choose the column that has the data's unique value, while making sure the data type. Usually it is the leftmost attribute in the dataset. And then just click next, next, and import.<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/15.png?raw=true) <br>
<br>

Now we wait for the import status to be finished. The quantity of datasets determines the import time. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/16.png?raw=true) <br>
<br>

Now that it's finished, go back to 'Explore items' menu and browse items to see the newly imported datasets.<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/17.png?raw=true) <br>
<br>

## **Scanning Data in DynamoDB**
Performing scans and searches can expedite the process of retrieving information. <br>
To begin, let's attempt a values scan on the data. Here, I opted for the "scan" option, followed by selecting the "table to scan" and specifying the "attributes to project filter" based on my search for Sales data. By applying filters, you can swiftly narrow down your search by specifying the desired attribute, such as "Overall" with a condition like "equal to 70" Once the necessary filters are set, simply click "run" to initiate the search. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/18.png?raw=true) <br>
<br>

Here is the results : <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/19.png?raw=true) <br>
<br>


## **Querying Data in DynamoDB**
The fact is, DynamoDB queries offer a wide range of sophisticated capabilities. However, for the purpose of this experiment, I will focus on utilizing queries that search for data using unique keys. Let's proceed with searching for unique data using these queries.<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/20.png?raw=true) <br>
<br>

You can choose query and then enter the partition key from your data in "ID" as a partition key. In this case, I'm using "6207". Here's the result : <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/21.png?raw=true) <br>
<br>

## **Exporting Data in DynamoDB**
Your table can be exported and stored on S3. Your first step should be to select "Export to S3" from the Dynamo DB menu. <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/22.png?raw=true) <br>
<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/23.png?raw=true) <br>
<br>
Then, a display of the export details will appear. You must fill out the source table you want to import and the S3 bucket's destination. Just try to export the table we created earlier :<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/24.png?raw=true) <br>
<br>

Wait until it's done :<br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/25.png?raw=true) <br>
<br>

Now is time to check the AWS bucket <br>
<br>
![image](https://github.com/vincentiussagi/bdcc/blob/main/26.png?raw=true) <br>
<br>
There it is! It will displayed as "AWSDynamoDB/.". Therefore, the export is finished.
<br>

## **Conclusion**
Amazon DynamoDB is a highly scalable and high-performance NoSQL database service. With a key-value storage model, DynamoDB provides low response times and high throughput. DynamoDB is also flexible in terms of data schemas, allowing arbitrary data storage. With high durability and fault tolerance, DynamoDB maintains high data availability. Overall, DynamoDB is a powerful NoSQL solution for managing large-scale data with fast performance and easy management. With DynamoDB, you can construct tables, import datasets, and run queries or scans to get the information you need.
















