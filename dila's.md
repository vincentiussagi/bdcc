# fadillazundina

Welcome to the fadillazundina wiki! <br>
# **Creating, Importing, Querying, and Exporting Data with Amazon DynamoDB**

## **DynamoDB**
Amazon DynamoDB is a fully managed NoSQL database service provided by Amazon Web Services (AWS). No-SQL database management solutions are those that depart from the traditional relational database model. For applications seeking speedy and dependable performance, even with a lot of data, it offers low latency, high availability, and seamless scaling. Due to DynamoDB's horizontal scalability, performance stays constant as data and traffic volumes increase by dispersing data across a number of servers. SSDs, which offer read and write operations with single-digit millisecond latency, are utilized for storage.<br>
<br>
Thanks to DynamoDB's schema-less data model, fixed table structures and predefined schemas are not required. The way the data is organized, with its tables and items, resembles a key-value store. This versatility enables agile development and easy adaptation to changing data requirements. Additionally, DynamoDB provides automated data replication and multi-region capabilities, ensuring exceptional availability and durability.

## **Create a Table in DynamoDB**
First, we search for "DynamoDB" in the AWS service menu. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/4fb618e9-401c-4a54-a05e-d6c66792e8fb) <br>
<br>

Then, to create a table, click "Create table". <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/a8238af2-4406-40a5-a827-250ff5d3df80) <br>
<br>

After that, a menu will display with options for configuring the table. Fill in the table name, partition key, and sort key (optional) in the table details. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/f6739a68-e61d-4b1a-be0e-3ead2776e441) <br>
<br>

Actually, users can alter the table's features, such as the capacity calculator and table class. I simply use the default parameters for this task.Click "Create Table" once all the settings have been made. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/801bd5b9-aacb-4551-a23f-d30955ff026e) <br>
<br>

Following creation, the table will appear in the DynamoDB tables list. Wait a short while for the status table to change to active if it is initially still developing.<br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/986ef652-4e53-4385-b020-f8332cb39ec9) <br>
<br>

Go to Explore items: your-table-name, select "Create item," enter the value for the table attribute, and then select "Create item" to add data to the table.<br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/171f5edb-d356-4d34-88b7-230858796545) <br>
<br>

You can also add new attributes by clicking "Add new attribute" in the upper right corner of the image above, keeping in mind the data type.<br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/48f99168-79a8-4418-9ba5-6cb8f3ee8610)<br>
<br>

## **Import Data**
Simply select DynamoDB from the menu, click Import from S3, and then select "Import from S3" to import datasets from an S3 bucket. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/4e0aeb49-94b9-4662-a4af-99d7d7b036e9) <br>
<br>

You can upload your files to the S3 bucket if you haven't already. In this case, I only need to navigate to the S3 directory since I have uploaded my files to S3. After that click "browse" to find the directory for the file to upload. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/7ebb9d43-8281-4df3-a28e-7f41b33e8c6f) <br>
<br>

Ensure that your file format matches your file format in the "Import file format" field. In this instance, I'm uploading from a csv file, so I click "Next" after selecting csv as the file format. <br>
<br>
<img width="608" alt="image" src="https://github.com/fadillazundina/fadillazundina/assets/100764121/e332bdc2-551c-4cf3-bb06-262afb2eb7e6"> <br>
<br>

Then, fill out the table details. For the partition keys, choose the column that has the data's unique value. And then just click next, next, and import.<br>
<br>
<img width="408" alt="image" src="https://github.com/fadillazundina/fadillazundina/assets/100764121/c48f2c59-2a00-4755-af2e-a56d7a48219a">
<br>

Simply wait for the import status to be finished. The quantity of datasets determines the import time. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/b054558c-9b1c-44f1-ab12-2579e74679fe) <br>
<br>

You can go back and browse items to see your newly imported datasets when the dataset has been fully loaded. And the image below shows how my dataset appears.<br>
<br>
<img width="607" alt="image" src="https://github.com/fadillazundina/fadillazundina/assets/100764121/065b9212-9484-453a-b6af-881f1fcbe1df"><br>
<br>

## **Scan Data**
Scanning and searching for data can help you uncover information more quickly. Let's try running a values ​​scan on the data first. I selected "scan" then "table to scan" and "attributes to project filter" because I was looking for Sales ($). You can quickly search using filters by filtering the value. in this case, I'm looking for the attribute "Sales ($)" when the value is "greater than or equal to 10.4". After that click "run". <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/ac50abcc-3d80-4cc9-a1fc-791ac886223d)<br>
<br>

Here is the outcome of my scanning, indicating that there are 194 rows of Advertising budget and sales with the Sales ($) when the value is greater than or equal to 10.4. <br>
<br>
<img width="602" alt="image" src="https://github.com/fadillazundina/fadillazundina/assets/100764121/b57596a1-4f34-40db-829d-890bfb81a6da"><br>
<br>

## **Querying Data**
In fact, dynamo database queries are very sophisticated, thus for the purposes of this experiment, I only employ queries that search for data using unique keys. Let's try searching for unique data. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/b6ff7d18-2d5f-40f7-abcc-a5656a11b617)<br>
<br>

You can choose query and then enter the partition key from your data in "ID" as a partition key. In this case, I'm using "79" to search for things with partition keys equal to 79, and the outcome is shown in the image below. <br>
<br>
<img width="598" alt="image" src="https://github.com/fadillazundina/fadillazundina/assets/100764121/d3ab8ecc-d854-4d85-aecd-e3e985adbf55"><br>
<br>

## **Export Data**
Your table can be exported and stored on S3. Your first step should be to select "Export to S3" from the Dynamo DB menu. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/d0c5c7f6-fe98-44f6-aed2-54190c098a10) <br>
<br>

Then, a display of the export details will appear. You must fill out the source table you want to import and the S3 bucket's destination. In this case, i've used the default settings for additional options. After that, click Export. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/c34dcf63-b539-4552-af6a-b1217fb5f4e0) <br>
<br>

Simply wait for the export table status to be completed. Once it is, the display will look like the one in the previous image. <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/2a30edaf-abd8-4da3-8610-6218f5576329)<br>
<br>

After that, let's check to the AWS bucket <br>
<br>
![image](https://github.com/fadillazundina/fadillazundina/assets/100764121/7f3f2922-0648-4f44-9059-7d9d06405672)<br>
<br>

As can be observed, exporting data from DynamoDB has resulted in the appearance of a new folder with the name "AWSDynamoDB/.". Therefore, the export is finished.
<br>

## **Conclusion**
Amazon DynamoDB is a highly scalable and high-performance NoSQL database service. With a key-value storage model, DynamoDB provides low response times and high throughput. DynamoDB is also flexible in terms of data schemas, allowing arbitrary data storage. With high durability and fault tolerance, DynamoDB maintains high data availability. Overall, DynamoDB is a powerful NoSQL solution for managing large-scale data with fast performance and easy management. With DynamoDB, you can construct tables, import datasets, and run queries or scans to get the information you need.
















