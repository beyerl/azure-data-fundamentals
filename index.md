---


---

<h1 id="explore-core-data-concepts">Explore core data concepts</h1>
<h2 id="explore-core-data-concepts-1">Explore core data concepts</h2>
<h3 id="identify-the-need-for-data-solutions">Identify the need for data solutions</h3>
<p>Data solutions include software technologies and platforms that can help facilitate the collection, analysis, and storage of valuable information. When analyzed properly, data provides a wealth of useful information and inform critical business decisions.</p>
<h4 id="what-is-data">What is data?</h4>
<p>Data is a collection of facts such as numbers, descriptions, and observations used in decision making. You can classify data as structured, semi-structured, or unstructured.</p>
<p>Structured data is typically tabular data that is represented by rows and columns in a database. Databases that hold tables in this form are called <em>relational databases</em> (the mathematical term <em>relation</em> refers to an organized set of data held as a table). Each row in a table has the same set of columns.</p>
<p><em>Semi-structured</em> data is information that doesn’t reside in a relational database but still has some structure to it. Examples include documents held in <em>JavaScript Object Notation</em>, <em>key-value</em> stores and <em>graph</em> database (JSON) format.</p>
<p>Not all data is structured or even semi-structured. For example, audio and video files, and binary data files might not have a specific structure. They’re referred to as <em>unstructured</em> data.</p>
<h4 id="how-is-data-defined-stored-and-accessed-in-cloud-computing">How is data defined, stored, and accessed in cloud computing?</h4>
<p>Depending on the type of data such as structured, semi-structured, or unstructured, data will be stored differently.</p>
<ul>
<li>Structured data is typically stored in a relational database such as SQL Server or Azure SQL Database.</li>
<li>If you want to store unstructured data such as video or audio files, you can use Azure Blob storage (<em>Blob</em> is an acronym for Binary Large Object).</li>
<li>If you want to store semi-structured data such as documents, you can use a service such as Azure Cosmos DB.</li>
</ul>
<p>The act of setting up the database server is called <em>provisioning</em>.</p>
<p>After your service is provisioned, the service needs to be configured so that users can be given access to the data. You can typically define several levels of access.</p>
<ul>
<li>
<p><em>Read-only</em> access means the users can read data but can’t modify any existing data or create new data.</p>
</li>
<li>
<p><em>Read/write</em> access gives users the ability to view and modify existing data.</p>
</li>
<li>
<p><em>Owner</em> privilege gives full access to the data including managing the security like adding new users and removing access to existing users.</p>
</li>
</ul>
<h4 id="describe-data-processing-solutions">Describe data processing solutions</h4>
<h5 id="what-is-a-transactional-system">What is a transactional system?</h5>
<p>A transactional system records <em>transactions</em>. Think of a transaction as a small, discrete, unit of work. A transaction could be financial, such as the movement of money between accounts in a banking system, or it might be part of a retail system, tracking payments for goods and services from customers.<br>
The work performed by transactional systems is often referred to as Online Transactional Processing (OLTP).<br>
To support fast processing, the data in a transactional system is often divided into small pieces. For example, if you’re using a relational system each table involved in a transaction only contains the columns necessary to perform the transactional task.<br>
Splitting tables out into separate groups of columns like this is called <em>normalized</em>.<br>
Normalization can enable a transactional system to cache much of the information required to perform transactions in memory, and speed throughput.</p>
<h5 id="what-is-an-analytical-system">What is an analytical system?</h5>
<p>Analytical systems are concerned with capturing raw data, and using it to generate insights. An organization can use these insights to make business decisions. Most analytical data processing systems need to perform similar tasks: data ingestion, data transformation, data querying, and data visualization.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-core-data-concepts/media/2-data-process.png" alt="Image depicting the elements of a typical data processing solution"></p>
<ul>
<li><strong>Data Ingestion</strong>: Data ingestion is the process of capturing the raw data.</li>
<li><strong>Data Transformation/Data Processing</strong>: The raw data might not be in a format that is suitable for querying. After data is ingested into a data repository, you may want to do some cleaning operations and remove any questionable or invalid data, or perform some aggregations such as calculating profit, margin, and other Key Performance Indicators (KPIs).</li>
<li><strong>Data Querying</strong>: After data is ingested and transformed, you can query the data to analyze it.</li>
<li><strong>Data Visualization</strong>: Visualizing the data can often be useful as a tool for examining data. You can generate charts such as bar charts, line charts, plot results on geographical maps, pie charts, or illustrate how data changes over time.</li>
</ul>
<h3 id="identify-types-of-data-and-data-storage">Identify types of data and data storage</h3>
<h4 id="describe-the-characteristics-of-relational-and-non-relational-data">Describe the characteristics of relational and non-relational data</h4>
<p>The simple structure of tables and columns makes <strong>relational databases</strong> easy to use initially, but the rigid structure can cause some problems.<br>
You can solve these problems by using a process called <em>normalization</em>. However, querying the data often requires reassembling information from multiple tables by joining the data back together at run-time (illustrated by the lines in the diagram). These types of queries can be expensive.</p>
<p><strong>Non-relational databases</strong> enable you to store data in a format that more closely matches the original structure. For example, in a document database, you could store the details of each customer in a single document. For example retrieving the details of a customer, including the address, is a matter of reading a single document. In a document database, the address would be duplicated in the documents for Jay and Francis Adams. This duplication not only increases the storage required, but can also make maintenance more complex.</p>
<h4 id="describe-transactional-workloads">Describe transactional workloads</h4>
<p>Relational and non-relational databases are suited to different workloads.</p>
<p>A primary use of relational databases is to handle transaction processing. A transaction is a sequence of operations that are <em>atomic</em>. This means that either all operations in the sequence must be completed successfully, or if something goes wrong, all operations run so far in the sequence must be undone.</p>
<p>Each database transaction has a defined beginning point, followed by steps to modify the data within the database. At the end, the database either commits the changes to make them permanent, or rolls back the changes to the starting point, when the transaction can be tried again.</p>
<p>A transactional database must adhere to the ACID (Atomicity, Consistency, Isolation, Durability) properties to ensure that the database remains consistent while processing transactions.</p>
<ul>
<li><em>Atomicity</em> guarantees that each transaction is treated as a single <em>unit</em>, which either succeeds completely, or fails completely.</li>
<li><em>Consistency</em> ensures that a transaction can only take the data in the database from one valid state to another. A consistent database should never <em>lose</em> or <em>create</em> data in a manner that can’t be accounted for.</li>
<li><em>Isolation</em> ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially. A concurrent process can’t see the data in an inconsistent state.</li>
<li><em>Durability</em> guarantees that once a transaction has been committed, it will remain committed even if there’s a system failure such as a power outage or crash.</li>
</ul>
<p>Database systems that process transactional workloads are inherently complex. They need to manage concurrent users possibly attempting to access and modify the same data at the same time, processing the transactions in isolation while keeping the database consistent and recoverable. Many systems implement relational consistency and isolation by applying locks to data when it is updated.  Extensive locking can lead to poor performance, while applications wait for locks to be released.</p>
<p>Distributed databases are widely used in many organizations. A distributed database is a database in which data is stored across different physical locations. When compared to non-distributed database systems, any data update to a distributed database will take time to apply across multiple locations. If you require transactional consistency in this scenario, locks may be retained for a very long time, especially if there’s a network failure between databases at a critical point in time. To counter this problem, many distributed database management systems relax the strict isolation requirements of transactions and implement <em>“eventual consistency.”</em> In this form of consistency, as an application writes data, each change is recorded by one server and then propagated to the other servers in the distributed database system asynchronously. While this strategy helps to minimize latency, it can lead to temporary inconsistencies in the data.</p>
<h4 id="describe-analytical-workloads">Describe analytical workloads</h4>
<p>Analytical workloads are typically read-only systems that store vast volumes of historical data or business metrics, such as sales performance and inventory levels. Analytical workloads are used for data analysis and decision making. Analytics are generated by aggregating the facts presented by the raw data into summaries, trends, and other kinds of <em>“Business information.”</em><br>
Transactional information, however, is an integral part of analytical information.</p>
<h3 id="describe-the-difference-between-batch-and-streaming-data">Describe the difference between batch and streaming data</h3>
<p>Data processing is simply the conversion of raw data to meaningful information through a process.</p>
<h4 id="understand-batch-processing">Understand batch processing</h4>
<p>In batch processing, newly arriving data elements are collected into a group. The whole group is then processed at a future time as a batch.</p>
<p>Advantages:</p>
<ul>
<li>Large volumes of data can be processed at a convenient time.</li>
<li>It can be scheduled to run at a time when computers or systems might otherwise be idle, such as overnight, or during off-peak hours.</li>
</ul>
<p>Disadvantages:</p>
<ul>
<li>The time delay between ingesting the data and getting the results.</li>
<li>All of a batch job’s input data must be ready before a batch can be processed. This means data must be carefully checked.</li>
</ul>
<h4 id="understand-streaming-and-real-time-data">Understand streaming and real-time data</h4>
<p>In stream processing, each new piece of data is processed when it arrives. For example, data ingestion is inherently a streaming process. Streaming handles data in real time. Streaming data processing is beneficial in most scenarios where new, dynamic data is generated on a continual basis. Stream processing is ideal for time-critical operations that require an instant real-time response.</p>
<h4 id="understand-differences-between-batch-and-streaming-data">Understand differences between batch and streaming data</h4>
<ul>
<li>
<p><em>Data Scope</em>: Batch processing can process all the data in the dataset. Stream processing typically only has access to the most recent data received, or within a rolling time window (the last 30 seconds, for example).</p>
</li>
<li>
<p><em>Data Size</em>: Batch processing is suitable for handling large datasets efficiently. Stream processing is intended for individual records or <em>micro batches</em> consisting of few records.</p>
</li>
<li>
<p><em>Performance</em>: The latency for batch processing is typically a few hours. Stream processing typically occurs immediately, with latency in the order of seconds or milliseconds.</p>
</li>
<li>
<p><em>Analysis</em>: You typically use batch processing for performing complex analytics. Stream processing is used for simple response functions, aggregates, or calculations such as rolling averages.</p>
</li>
</ul>
<h2 id="explore-roles-and-responsibilities-in-the-world-of-data">Explore roles and responsibilities in the world of data</h2>
<h3 id="explore-job-roles-in-the-world-of-data">Explore job roles in the world of data</h3>
<h4 id="what-are-the-roles-in-the-world-of-data">What are the roles in the world of data?</h4>
<ul>
<li><strong>Database Administrators</strong> manage databases, assigning permissions to users, storing backup copies of data and restore data in case of any failures.</li>
<li><strong>Data Engineers</strong> are vital in working with data, applying data cleaning routines, identifying business rules, and turning data into useful information.</li>
<li><strong>Data Analysts</strong> explore and analyze data to create visualizations and charts to enable organizations to make informed decisions.</li>
</ul>
<h4 id="azure-database-administrator-role">Azure Database Administrator role</h4>
<p>An Azure database administrator is responsible for the design, implementation, maintenance, and operational aspects of on-premises and cloud-based database solutions built on Azure data services and SQL Server. The database administrator is also responsible for managing the security of the data in the database, granting privileges over the data, granting or denying access to users as appropriate.</p>
<h4 id="data-engineer-role">Data Engineer role</h4>
<p>A data engineer collaborates with stakeholders to design and implement data-related assets that include data ingestion pipelines, cleansing and transformation activities, and data stores for analytical workloads.</p>
<p>They’re also responsible for ensuring that the privacy of data is maintained within the cloud and spanning from on-premises to the cloud data stores. They also own the management and monitoring of data stores and data pipelines to ensure that data loads perform as expected.</p>
<h4 id="data-analyst-role">Data Analyst role</h4>
<p>A data analyst enables businesses to maximize the value of their data assets. They’re responsible for designing and building scalable models, cleaning and transforming data, and enabling advanced analytics capabilities through reports and visualizations.<br>
A data analyst processes raw data into relevant insights based on identified business requirements to deliver relevant insights.</p>
<h3 id="review-tasks-and-tools-for-database-administration">Review tasks and tools for database administration</h3>
<h4 id="database-administrator-tasks-and-responsibilities">Database Administrator tasks and responsibilities</h4>
<p>Some of the most common roles and responsibilities of a database administrator include:</p>
<ul>
<li>Installing and upgrading the database server and application tools.</li>
<li>Allocating system storage and planning storage requirements for the database system.</li>
<li>Modifying the database structure, as necessary, from information given by application developers.</li>
<li>Enrolling users and maintaining system security.</li>
<li>Ensuring compliance with database vendor license agreement.</li>
<li>Controlling and monitoring user access to the database.</li>
<li>Monitoring and optimizing the performance of the database.</li>
<li>Planning for backup and recovery of database information.</li>
<li>Maintaining archived data.</li>
<li>Backing up and restoring databases.</li>
<li>Contacting database vendor for technical support.</li>
<li>Generating various reports by querying from database as per need.</li>
<li>Managing and monitoring data replication.</li>
</ul>
<h4 id="common-database-administrator-tools">Common database administrator tools</h4>
<p>Most database management systems provide their own set of tools to assist with database administration.</p>
<ul>
<li><em>SQL Server Management Studio</em> for T-SQL (Transact-SQL)</li>
<li><em>pgAdmin</em> for PostgreSQL</li>
<li><em>MySQL Workbench</em> for MySQL.</li>
</ul>
<h5 id="what-is-azure-data-studio">What is Azure Data Studio?</h5>
<p>Azure Data Studio provides a graphical user interface for managing many different database systems.</p>
<h5 id="use-the-azure-portal-to-manage-azure-sql-database">Use the Azure portal to manage Azure SQL Database</h5>
<p>You can manage Azure SQL database using Azure portal.</p>
<h3 id="review-tasks-and-tools-for-data-engineering">Review tasks and tools for data engineering</h3>
<h4 id="data-engineer-tasks-and-responsibilities">Data Engineer tasks and responsibilities</h4>
<p>Some of the most common roles and responsibilities of a data engineer include:</p>
<ul>
<li>Developing, constructing, testing, and maintaining databases and data structures.</li>
<li>Aligning the data architecture with business requirements.</li>
<li>Data acquisition.</li>
<li>Developing processes for creating and retrieving information from data sets.</li>
<li>Using programming languages and tools to examine the data.</li>
<li>Identifying ways to improve data reliability, efficiency, and quality.</li>
<li>Conducting research for industry and business questions.</li>
<li>Deploying sophisticated analytics programs, machine learning, and statistical methods.</li>
<li>Preparing data for predictive and prescriptive modeling.</li>
<li>Using data to discover tasks that can be automated.</li>
</ul>
<h4 id="common-data-engineering-tools">Common data engineering tools</h4>
<p>To master data engineering, you’ll need to be familiar with a range of tools that enable you to create well-designed databases, optimized for the business processes that will be run. You must have a thorough understanding of the architecture of the database management system, the platform on which the system runs, and the business requirements for the data being stored in the database.<br>
If you’re using a relational database management system, you need to be fluent in SQL.<br>
In some cases, you may need to interact with a database from the command line. For example, you can use the <em>sqlcmd</em> utility to connect to Microsoft SQL Server and Azure SQL Database, and run ad-hoc queries and commands.<br>
As a SQL Server professional, your primary data manipulation tool might be Transact-SQL. As a data engineer you might use additional technologies, such as <a href="https://docs.microsoft.com/en-us/azure/azure-databricks/what-is-azure-databricks">Azure Databricks</a>, and <a href="https://docs.microsoft.com/en-us/azure/hdinsight/hdinsight-overview">Azure HDInsight</a> to generate and test predictive models. If you’re working in the non-relational field, you might use <a href="https://docs.microsoft.com/en-us/azure/cosmos-db/introduction">Azure Cosmos DB</a> as your primary data store. To manipulate and query the data, you might use languages such as HiveQL, R, or Python.</p>
<h3 id="review-tasks-and-tools-for-data-visualization-and-reporting">Review tasks and tools for data visualization and reporting</h3>
<h4 id="data-analyst-tasks-and-responsibilities">Data Analyst tasks and responsibilities</h4>
<p>The primary functions of a data analyst usually include the following:</p>
<ul>
<li>Making large or complex data more accessible, understandable, and usable.</li>
<li>Creating charts and graphs, histograms, geographical maps, and other visual models that help to explain the meaning of large volumes of data, and isolate areas of interest.</li>
<li>Transforming, improving, and integrating data from many sources, depending on the business requirements.</li>
<li>Combining the data result sets across multiple sources. For example, combining sales data and weather data provides a useful insight into how weather influenced sales of certain products such as ice creams.</li>
<li>Finding hidden patterns using data.</li>
<li>Delivering information in a useful and appealing way to users by creating rich graphical dashboards and reports.</li>
</ul>
<h4 id="common-data-visualization-tools">Common data visualization tools</h4>
<p>Power BI is a collection of software services, apps, and connectors that work together to turn your unrelated sources of data into coherent, visually immersive, and interactive insights.</p>
<h2 id="describe-concepts-of-relational-data">Describe concepts of relational data</h2>
<h3 id="explore-the-characteristics-of-relational-data">Explore the characteristics of relational data</h3>
<p>One of the main benefits of computer databases is that they make it easy to store information so it’s quick and easy to find. A relational database provides a model for storing the data, and a query capability that enables you to retrieve data quickly.</p>
<h4 id="understand-the-characteristics-of-relational-data">Understand the characteristics of relational data</h4>
<p>The main characteristics of a relational database are:</p>
<ul>
<li>
<p>All data is tabular. Entities are modeled as tables, each instance of an entity is a row in the table, and each property is defined as a column.</p>
</li>
<li>
<p>All rows in the same table have the same set of columns.</p>
</li>
<li>
<p>A table can contain any number of rows.</p>
</li>
<li>
<p>A primary key uniquely identifies each row in a table. No two rows can share the same primary key.</p>
</li>
<li>
<p>A foreign key references rows in another, related table. For each value in the foreign key column, there should be a row with the same value in the corresponding primary key column in the other table.</p>
</li>
</ul>
<p>The lines connecting the tables indicate the type of relationship:</p>
<ul>
<li><em>1-to-many</em>: one customer can place many orders, but each order is for a single customer.</li>
<li><em>many-to-1</em>: several orders might be for the same product.</li>
</ul>
<p>Most relational databases support Structured Query Language (SQL). You use SQL to create tables, insert, update, and delete rows in tables, and to query data.</p>
<h4 id="explore-relational-database-use-cases">Explore relational database use cases</h4>
<p>You can use a relational database any time you can easily model your data as a collection of tables with a fixed set of columns.</p>
<p>Relational databases are commonly used in ecommerce systems, but one of the major use cases for using relational databases is Online Transaction Processing (OLTP). OLTP applications are focused on transaction-oriented tasks that process a very large number of transactions per minute.</p>
<h3 id="explore-relational-data-structures">Explore relational data structures</h3>
<h4 id="what-is-an-index">What is an index?</h4>
<p>An index helps you search for data in a table. Think of an index over a table like an index at the back of a book. When you create an index in a database, you specify a column from the table, and the index contains a copy of this data in a sorted order, with pointers to the corresponding rows in the table. When the user runs a query that specifies this column in the <em>WHERE</em> clause, the database management system can use this index to fetch the data more quickly than if it had to scan through the entire table row by row.</p>
<p>You can create many indexes on a table. However, indexes aren’t free. An index might consume additional storage space, and each time you insert, update, or delete data in a table, the indexes for that table must be maintained. This additional work can slow down insert, update, and delete operations, and incur additional processing charges.</p>
<p>Some relational database management systems also support <em>clustered indexes</em>. A clustered index physically reorganizes a table by the index key. This arrangement can improve the performance of queries still further, because the relational database management system doesn’t have to follow references from the index to find the corresponding data in the underlying table.</p>
<h4 id="what-is-a-view">What is a view?</h4>
<p>A view is a virtual table based on the result set of a query. You can query the view and filter the data in much the same way as a table.</p>
<h3 id="choose-the-right-platform-for-a-relational-workload">Choose the right platform for a relational workload</h3>
<p>Relational database management systems are one example of where the cloud has enabled organizations to take advantage of improved scalability. However, this scalability has to be balanced against the need for close control over the data. Data is arguably one of the most valuable assets that an organization has, and some companies aren’t willing or able to hand over responsibility for protecting this data to a third party.</p>
<h4 id="compare-on-premises-hosting-to-the-cloud">Compare on-premises hosting to the cloud</h4>
<p>Whether a company places its relational workload in the cloud or whether it decides to keep it on premises, data security will always be paramount.</p>
<p>Hosting a relational database on-premises requires that an enterprise not only purchases the database software, but also maintains the necessary hardware on which to run the database. Scalability is also a concern. If you need to scale your system, you will need to upgrade or add more servers.</p>
<p>A cloud-based approach uses virtual technology to host a company’s applications offsite. There are no capital expenses, data can be backed up regularly, and companies only have to pay for the resources they use. For those organizations that plan aggressive expansion on a global basis, the cloud has even greater appeal because it allows you to connect with customers, partners, and other businesses anywhere with minimal effort. Additionally, cloud computing gives you nearly instant provisioning because everything is already configured.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/describe-concepts-of-relational-data/media/4-on-premises-cloud.png" alt="Compare on-premises with cloud"></p>
<h4 id="understand-iaas-and-paas">Understand IaaS and PaaS</h4>
<p><strong>IaaS</strong> is an acronym for <em>Infrastructure-as-a-Service</em>. Azure enables you to create a virtual infrastructure in the cloud that mirrors the way an on-premises data center might work.<br>
The IaaS approach is best for migrations and applications requiring operating system-level access. SQL virtual machines are <em>lift-and-shift</em>. That is, you can copy your on-premises solution directly to a virtual machine in the cloud.</p>
<p><strong>PaaS</strong> stands for <em>Platform-as-a-service</em>. Rather than creating a virtual infrastructure, and installing and managing the database software yourself, a PaaS solution does this for you.<br>
Azure offers several PaaS solutions for relational databases, include Azure SQL Database, Azure Database for PostgreSQL, Azure Database for MySQL, and Azure Database for MariaDB. These services run managed versions of the database management systems on your behalf. However, you may find that there are some functional restrictions in place, and not every feature of your selected database management system may be available. These restrictions are often due to security issues. In these cases, you may need to rework your applications to remove any dependencies on these features.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/describe-concepts-of-relational-data/media/4-choose-platform.png" alt="Various options of database workloads in Azure"></p>
<h2 id="explore-concepts-of-non-relational-data">Explore concepts of non-relational data</h2>
<h3 id="explore-characteristics-of-non-relational-data">Explore characteristics of non-relational data</h3>
<p>In some situations, you might not have the required knowledge of the structure of your data, in advance of it arriving in your database, to record it as a neat set of rows and columns in a tabular format. This is a common scenario in systems that consume data from a wide variety of sources, such as data ingestion pipelines. In these situations, a non-relational database can prove extremely useful.</p>
<h4 id="what-are-the-characteristics-of-non-relational-data">What are the characteristics of non-relational data?</h4>
<p>You use a database to model some aspect of the real-world. Entities in the real-world often have highly variable structures.</p>
<p>In another scenario, if you are ingesting data rapidly, you want to capture the data and save it very quickly. Processing the data and manipulating it into a set of rows in different tables in a relational database might not be appropriate at this point; you can perform these tasks at a later date.</p>
<p>A key aspect of non-relational databases is that they enable you to store data in a very flexible manner. Non-relational databases don’t impose a schema on data. Instead, they focus on the data itself rather than how to structure it. This approach means that you can store information in a natural format, that mirrors the way in which you would consume, query and use it.</p>
<p>In a non-relational system, you store the information for entities in collections or containers rather than relational tables. The lack of a fixed schema means that each entity must be self-describing.</p>
<p>An application that queries this data must be prepared to parse the information in the entity that it retrieves.</p>
<p>The data retrieval capabilities of a non-relational database can vary. Each entity should have a unique key value. The entities in a collection are usually stored in key-value order. Filtering data on fields other than the key would require scanning the entire collection of entities, parsing each entity in turn, and then applying any query criteria to each entity to find any matches. More advanced non-relational systems support indexing, in a similar manner to an index in a relational database.</p>
<h4 id="identify-non-relational-database-use-cases">Identify non-relational database use cases</h4>
<ul>
<li><em>IoT and telematics</em>. These systems typically ingest large amounts of data in frequent bursts of activity. Non-relational databases can store this information very quickly.</li>
<li><em>Retail and marketing</em>. E.g. for storing catalog data and for event sourcing in order processing pipelines.</li>
<li><em>Gaming</em>. Games often require single-millisecond latencies for reads and write to provide an engaging in-game experience. A game database needs to be fast and be able to handle massive spikes in request rates during new game launches and feature updates.</li>
<li><em>Web and mobile applications</em>. A non-relational database such as Azure Cosmos DB is commonly used within web and mobile applications, and is well suited for modeling social interactions, integrating with third-party services, and for building rich personalized experiences.</li>
</ul>
<h3 id="describe-types-of-non-relational-data">Describe types of non-relational data</h3>
<h4 id="what-is-semi-structured-data">What is semi-structured data?</h4>
<p>Semi-structured data is data that contains fields. The fields don’t have to be the same in every entity. You only define the fields that you need on a per-entity basis. The data must be formatted in such a way that an application can parse and process it. One common way of doing this is to store the data for each entity as a JSON document.</p>
<pre><code>{
  "ID": "1",
  "Name": "Mark Hanson",
  "Telephone": [ 
    { "Home": "1-999-9999999" }, 
    { "Business": "1-888-8888888" }, 
    { "Cell": "1-777-7777777" }
  ],
  "Address": [ 
    { "Home": [
      { "StreetAddress": "121 Main Street" }, 
      { "City": "Some City" },
      { "State": "NY" }, 
      { "Zip": "10110" }
    ] },
    { "Business": [
      { "StreetAddress": "87 Big Building" },
      { "City": "Some City" },
      { "State": "NY" },
      { "Zip": "10111" }
    ] }
  ] 
}


{
  "ID": "2",
  "Title": "Mr",
  "Name": "Jeff Hay",
  "Telephone": [ 
    { "Home": "0044-1999-333333" }, 
    { "Mobile": "0044-17545-444444" }
  ],
  "Address": [
    { "UK": [
      { "StreetAddress": "86 High Street" },
      { "Town": "Some Town" }, 
      { "County": "A County" }, 
      { "Postcode": "GL8888" }, 
      { "Region": "UK" }
    ] },
    { "US": [
      { "StreetAddress": "777 7th Street" }, 
      { "City": "Another City" },
      { "State": "CA" },
      { "Zip": "90111" }
    ] }
  ]
}
</code></pre>
<p>Other formats you might see include <em>Avro</em>, <em>ORC</em>, and <em>Parquet</em>:</p>
<ul>
<li><em>Avro</em> is a row-based format. It was created by Apache. Each record contains a header that describes the structure of the data in the record. Each record contains a header that describes the structure of the data in the record. This header is stored as JSON. The data is stored as binary information. This example is a subset of the header information for the previous example, formatted as Avro:</li>
</ul>
<pre><code>{
  "type": "record",
  "name": "contact_schema",
  "fields": [
   {
      "name": "id",
      "type": "int",
      "doc": "ID of the contact"
    },
    {
      "name": "name",
      "type": "string",
      "doc": "Name of the contact"
    },
{
      "name": "telephone",
      "type": [
        "null",
        {
          "type": "array",
          "items": {
            "type": "record",
            "name": "contact_schema.telephone",
            "fields": [
              {
                "name": "phoneid",
                "type": "int"
              },
              {
                "name": "phonetype",
                "type": [ "null", "string" ]
              }
            ]
          }
        }
      ]
    }
  ]
}
</code></pre>
<ul>
<li><em>ORC</em> (Optimized Row Columnar format) organizes data into columns rather than rows. It was developed by HortonWorks for optimizing read and write operations in Apache Hive. Hive is a data warehouse system that supports fast data summarization and querying over very large datasets.</li>
<li><em>Parquet</em> is another columnar data format. It was created by Cloudera and Twitter. A Parquet file contains row groups. Data for each column is stored together in the same row group. Each row group contains one or more chunks of data.</li>
</ul>
<h4 id="what-is-unstructured-data">What is unstructured data?</h4>
<p>Unstructured data is data that doesn’t naturally contain fields. Examples include video, audio, and other media streams. Each item is an amorphous blob of binary data. You can’t search for specific elements in this data.</p>
<p>In Azure, you would probably store video and audio data as block blobs in an Azure Storage account. (The term <em>blob</em> stands for Binary Large Object*).</p>
<p>You could also consider files as a form of unstructured data, although in some cases a file might include metadata that indicates what type of file it is (photograph, Word document, Excel spreadsheet, and so on), owner, and other elements that could be stored as fields.</p>
<h3 id="describe-types-of-non-relational-and-nosql-databases">Describe types of non-relational and NoSQL databases</h3>
<h4 id="what-is-nosql">What is NoSQL?</h4>
<p>NoSQL is a rather loose term that simply means non-relational. There’s some debate about whether it’s intended to imply <em>Not SQL</em>, or <em>Not Only SQL</em>.</p>
<p>NoSQL (non-relational) databases generally fall into four categories: key-value stores, document databases, column family databases, and graph databases.</p>
<h4 id="what-is-a-key-value-store">What is a key-value store?</h4>
<p>A key-value store is the simplest (and often quickest) type of NoSQL database for inserting and querying data. Each data item in a key-value store has two elements, a key and a value.</p>
<ul>
<li>
<p>The key uniquely identifies the item, and the value holds the data for the item.</p>
</li>
<li>
<p>The value is <em>opaque</em> to the database management system. The term <em>opaque</em> means that the database management system just sees the value as an unstructured block.<br>
Items are stored in key order.</p>
</li>
<li>
<p>A query specifies the keys to identify the items to be retrieved.</p>
</li>
<li>
<p>You can’t search on values.</p>
</li>
<li>
<p>Write operations are restricted to inserts and deletes. If you need to update an item, you must retrieve the item, modify it in memory (in the application), and then write it back to the database, overwriting the original (effectively a delete and an insert).</p>
</li>
</ul>
<p>The focus of a key-value store is the ability to read and write data very quickly.</p>
<p>Azure Table storage is an example of a key-value store. Cosmos DB also implements a key-value store using the Table API.</p>
<h4 id="what-is-a-document-database">What is a document database?</h4>
<ul>
<li>
<p>In a document database, each document has a unique ID, but the fields in the documents are transparent to the database management system.</p>
</li>
<li>
<p>Document databases typically store data in JSON format, as described in the previous unit, or they could be encoded using other formats such as XML, YAML, JSON, BSON. Documents could even be stored as plain text.</p>
</li>
<li>
<p>The fields in documents are exposed to the storage management system, enabling an application to query and filter data by using the values in these fields.</p>
</li>
<li>
<p>Typically, a document contains the entire data for an entity. A single document may contain information that would be spread across several relational tables in an RDBMS (relational database management system).</p>
</li>
<li>
<p>A document store does not require that all documents have the same structure.</p>
</li>
</ul>
<h4 id="what-is-a-column-family-database">What is a column family database?</h4>
<p>A column family database organizes data into rows and columns. Examples of this structure include ORC and Parquet files, described in the previous unit.</p>
<p>In its simplest form, a column family database can appear very similar to a relational database, at least conceptually. The real power of a column family database lies in its denormalized approach to structuring sparse data.<br>
For example, if you need to store information about customers and their addresses in a relational database (ignoring the need to maintain historical data as described in the previous section), you might design a schema similar to that shown below. This diagram also shows some sample data. In this example, customer 1 and customer 3 share the same address, and the schema ensures that this address information is not duplicated. This is a standard way of implementing a one-to-many relationship.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-non-relational-data/media/4-relational.png" alt="Relational structure showing customers and addresses"></p>
<p>The relational model supports a very generalized approach to implementing this type of relationship, but to find the address of any given customer an application needs to run a query that joins two tables. If this is the most common query performed by the application, then the overhead associated with performing this join operation can quickly become significant if there are a large number of requests and the tables themselves are large.</p>
<p>The purpose of a column family database is to efficiently handle situations such as this. You can think of a column family database as holding tabular data comprising rows and columns, but you can divide the columns into groups known as column-families. Each column family holds a set of columns that are logically related together. The image below shows one way of structuring the same information as the previous image, by using a column family database to group the data into two column-families holding the customer name and address information. Other ways of organizing the columns are possible, but you should implement your column-families to optimize the most common queries that your application performs.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-non-relational-data/media/4-column-family.png" alt="Example of a column family database">In most column family databases, the column-families are stored separately. The data for a single entity that spans multiple column-families will have the same row key in each column family. As an alternative to the conceptual layout shown previously, you can visualize the data shown as the following pair of physical structures.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-non-relational-data/media/4-column-family-physical.png" alt="The physical structure of a column family database"><br>
The most widely used column family database management system is Apache Cassandra. Azure Cosmos DB supports the column-family approach through the Cassandra API.</p>
<h4 id="what-is-a-graph-database">What is a graph database?</h4>
<p>Graph databases enable you to store entities, but the main focus is on the relationships that these entities have with each other. A graph database stores two types of information: nodes that you can think of as instances of entities, and edges, which specify the relationships between nodes. Nodes and edges can both have properties that provide information about that node or edge (like columns in a table). Additionally, edges can have a direction indicating the nature of the relationship.</p>
<p>The purpose of a graph database is to enable an application to efficiently perform queries that traverse the network of nodes and edges, and to analyze the relationships between entities. You can often store the same information in a relational database, but the SQL required to query this information might require many expensive recursive join operations and nested subqueries.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-non-relational-data/media/4-graph.png" alt="Graph Store"></p>
<p>Azure Cosmos DB supports graph databases using the Gremlin API. The Gremlin API is a standard language for creating and querying graphs.</p>
<h2 id="explore-concepts-of-data-analytics">Explore concepts of data analytics</h2>
<h3 id="describe-data-ingestion-and-processing">Describe data ingestion and processing</h3>
<p>Data analytics is concerned with taking data and finding meaningful information and inferences from it.<br>
The data a company uses can come from many sources. In a data analytics solution, you combine this data and construct a data warehouse that you can use to ask (and answer) questions about your business operations. Building a data warehouse requires that you can capture the data that you need and <em>wrangle</em> it into an appropriate format. You can then use analysis tools and visualizations to examine the information, and identify trends and their causes. <em>Wrangling</em> is the process by which you transform and map raw data into a more useful format for analysis.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/2-data-process.png" alt="A typical data analytics architecture depicting data ingestion, processing, and exploration"></p>
<h4 id="what-is-data-ingestion">What is data ingestion?</h4>
<p>Data ingestion is the process of obtaining and importing data for immediate use or storage in a database. The data can arrive as a continuous stream, or it may come in batches, depending on the source. The purpose of the ingestion process is to capture this data and store it. This raw data can be held in a repository such as a database management system, a set of files, or some other type of fast, easily accessible storage. The ingestion process might also perform filtering.  It may also be possible to perform some transformations at this stage, converting data into a standard form for later processing. However, these transformations must be quick to perform.</p>
<h4 id="what-is-data-processing">What is data processing?</h4>
<p>The data processing stage occurs after the data has been ingested and collected. Data processing takes the data in its raw form, cleans it, and converts it into a more meaningful format (tables, graphs, documents, and so on). The result is a database of data that you can use to perform queries and generate visualizations. Data cleaning is a generalized term that encompasses a range of actions, such as removing anomalies, and applying filters and transformations that would be too time-consuming to run during the ingestion stage.</p>
<p>The aim of data processing is to convert the raw data into one or more business models. A business model describes the data in terms of meaningful business entities, and may aggregate items together and summarize information.</p>
<p>The data processing stage could also generate predictive or other analytical models from the data. Data processing can be complex, and may involve automated scripts, and tools such as Azure Databricks, Azure Functions, and Azure Cognitive Services to examine and reformat the data, and generate models. A data analyst could use machine learning to help determine future trends based on these models.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/2-process-stage.png" alt="Processing ingested data to generate data models"></p>
<h4 id="what-is-elt-and-etl">What is ELT and ETL?</h4>
<p>ETL stands for <em>Extract, Transform, and Load</em>. The raw data is retrieved and transformed before being saved. The extract, transform, and load steps can be performed as a continuous pipeline of operations. It is suitable for systems that only require simple models, with little dependency between items. For example, this type of process is often used for basic data cleaning tasks, deduplicating data, and reformatting the contents of individual fields.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/2-extract-transform-load.png" alt="Image showing the ETL process"></p>
<p>An alternative approach is <em>ELT</em>. ELT is an abbreviation of <em>Extract, Load, and Transform</em>. The process differs from ETL in that the data is stored before being transformed. The data processing engine can take an iterative approach, retrieving and processing the data from storage, before writing the transformed data and models back to storage. ELT is more suitable for constructing complex models that depend on multiple items in the database, often using periodic batch processing.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/2-extract-load-transform.png" alt="Image showing the ELT process"></p>
<p>ELT is a scalable approach that is suitable for the cloud because it can make use of the extensive processing power available. However, ETL can filter data before it’s stored. In this way, ETL can help with data privacy and compliance, removing sensitive data before it arrives in your analytical data models.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/2-etl-vs-elt.png" alt="ETL versus ELT"></p>
<h3 id="explore-data-visualization">Explore data visualization</h3>
<p>A business model can contain an enormous amount of information. The purpose of producing a model such as this is to help you reason over the information it contains, ask questions, and hopefully obtain answers that can help you drive your business forward.</p>
<h4 id="what-is-reporting">What is reporting?</h4>
<p>Reporting is the process of organizing data into informational summaries to monitor how different areas of an organization are performing.</p>
<h4 id="what-is-business-intelligence">What is business intelligence?</h4>
<p>The term <em>Business Intelligence</em> (BI) refers to technologies, applications, and practices for the collection, integration, analysis, and presentation of business information. The purpose of business intelligence is to support better decision making.<br>
Information is often gathered about other companies in the same industry for comparison. This process of comparison with other companies in the same industry is known as <em>benchmarking</em>.</p>
<h4 id="what-is-data-visualization">What is data visualization?</h4>
<p>Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to spot and understand trends, outliers, and patterns in data. If you are using Azure, the most popular data visualization tool is Power BI.</p>
<h5 id="explore-visualization-options-to-represent-data">Explore visualization options to represent data</h5>
<p>Data visualization helps you to focus on the meaning of data, rather than looking at the data itself.</p>
<p>The most common forms of visualizations are:</p>
<ul>
<li><em>Bar and column charts</em>: Bar and column charts enable you to see how a set of variables changes across different categories.</li>
<li><em>Line charts</em>: Line charts emphasize the overall shape of an entire series of values, usually over time.</li>
<li><em>Matrix</em>: A matrix visual is a tabular structure that summarizes data.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/3-matrix.png" alt="Example of a Matrix Visual">- <em>Key influencers</em>: A key influencer chart displays the major contributors to a selected result or value.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/3-influencer.png" alt="Example of a Key influencers Visual">- <em>Treemap</em>: Treemaps are charts of colored rectangles, with size representing the relative value of each item. They can be hierarchical, with rectangles nested within the main rectangles.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/3-treemap.png" alt="Example of a treemap Visual"></li>
<li><em>Scatter</em>: A scatter chart shows the relationship between two numerical values. A <em>bubble chart</em> is a scatter chart that replaces data points with bubbles, with the bubble size representing an additional third data dimension.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/3-bubble.png" alt="Example of a bubble Visual">A dot plot chart is similar to a bubble chart and scatter chart, but can plot categorical data along the X-Axis.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/3-dotplot.png" alt="Example of a dotplot Visual">-   <em>Filled map</em>. If you have geographical data, you can use a filled map to display how a value differs in proportion across a geography or region. You can see relative differences with shading that ranges from light (less-frequent/lower) to dark (more-frequent/more).<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/3-filled-map.png" alt="Example of a filled map Visual"></li>
</ul>
<h3 id="explore-data-analytics">Explore data analytics</h3>
<p>Data analytics is concerned with examining, transforming, and arranging data so that you can study it and extract useful information. Data analytics is a discipline that covers the entire range of data management tasks. These tasks not only include analysis, but also data collection, organization, storage, and all the tools and techniques used.</p>
<p>The term <em>data analytics</em> is a catch-all that covers a range of activities, each with its own focus and goals. You can categorize these activities as <em>descriptive</em>, <em>diagnostic</em>, <em>predictive</em>, <em>prescriptive</em>, and <em>cognitive</em> analytics.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-concepts-of-data-analytics/media/4-analytics-table.png" alt="Categories of analytics"></p>
<h4 id="descriptive-analytics">Descriptive analytics</h4>
<p>Descriptive analytics helps answer questions about what has happened, based on historical data. Descriptive analytics techniques summarize large datasets to describe outcomes to stakeholders.<br>
By developing KPIs (Key Performance Indicators), these strategies can help track the success or failure of key objectives.<br>
Examples of descriptive analytics include generating reports to provide a view of an organization’s sales and financial data.</p>
<h4 id="diagnostic-analytics">Diagnostic analytics</h4>
<p>Diagnostic analytics helps answer questions about why things happened. Diagnostic analytics techniques supplement more basic descriptive analytics. They take the findings from descriptive analytics and dig deeper to find the cause. The performance indicators are further investigated to discover why they got better or worse. This generally occurs in three steps:</p>
<ol>
<li>Identify anomalies in the data. These may be unexpected changes in a metric or a particular market.</li>
<li>Collect data that’s related to these anomalies.</li>
<li>Use statistical techniques to discover relationships and trends that explain these anomalies.</li>
</ol>
<h4 id="predictive-analytics">Predictive analytics</h4>
<p>Predictive analytics helps answer questions about what will happen in the future. Predictive analytics techniques use historical data to identify trends and determine if they’re likely to recur. Techniques include a variety of statistical and machine learning techniques such as neural networks, decision trees, and regression.</p>
<h4 id="prescriptive-analytics">Prescriptive analytics</h4>
<p>Prescriptive analytics helps answer questions about what actions should be taken to achieve a goal or target. By using insights from predictive analytics, data-driven decisions can be made. This technique allows businesses to make informed decisions in the face of uncertainty. Prescriptive analytics techniques rely on machine learning strategies to find patterns in large datasets. By analyzing past decisions and events, the likelihood of different outcomes can be estimated.</p>
<h4 id="cognitive-analytics">Cognitive analytics</h4>
<p>Cognitive analytics attempts to draw inferences from existing data and patterns, derive conclusions based on existing knowledge bases, and then add these findings back into the knowledge base for future inferences–a self-learning feedback loop. Cognitive analytics helps you to learn what might happen if circumstances change, and how you might handle these situations.<br>
Effective cognitive analytics depends on machine learning algorithms. It uses several NLP (Natural Language Processing) concepts to make sense of previously untapped data sources, such as call center conversation logs and product reviews.</p>
<p><a href="https://docs.microsoft.com/de-de/learn/paths/azure-data-fundamentals-explore-relational-data/">hier weiter</a></p>

