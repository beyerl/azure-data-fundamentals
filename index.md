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
<h2 id="azure-data-fundamentals-explore-relational-data-in-azure"># Azure Data Fundamentals: Explore relational data in Azure</h2>
<h3 id="explore-relational-data-services-in-azure">Explore relational data services in Azure</h3>
<p>Azure offers a range of options for running a database management system in the cloud. For example, you can migrate your on-premises systems to a collection of Azure virtual machines. This approach still requires that you manage your database management system (DBMS) carefully. Alternatively, you can take advantage of the various Azure relational data services available. These data services manage the DBMS for you, leaving you free to concentrate on the data they contain and the applications that use them.</p>
<h4 id="understand-iaas-paas-and-saas">Understand IaaS, PaaS, and SaaS</h4>
<p><strong>IaaS</strong> is an acronym for <em>Infrastructure-as-a-Service</em>. Azure enables you to create a virtual infrastructure in the cloud that mirrors the way an on-premises data center might work.<br>
<strong>PaaS</strong> stands for <em>Platform-as-a-service</em>. Rather than creating a virtual infrastructure, and installing and managing the database software yourself, a PaaS solution does this for you.<br>
<strong>SaaS</strong> is short for <em>Software-as-a-Service</em>. SaaS services are typically specific software packages that are installed and run on virtual hardware in the cloud. SaaS packages are typically hosted applications rather than more generalized software such as a DBMS.<br>
<img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-relational-data-offerings/media/2-saas-paas-iaas.png" alt="IaaS, PaaS, and Saas"></p>
<h3 id="what-are-azure-data-services">What are Azure Data Services?</h3>
<p>Azure Data Services fall into the PaaS category. These services are a series of DBMSs managed by Microsoft in the cloud.</p>
<p>Azure Data Services are available for several common relational database management systems. The most well-known service is Azure SQL Database. The others currently available are Azure Database for MySQL servers, Azure Database for MariaDB servers, and Azure Database for PostgreSQL servers.</p>
<p>Using Azure Data Services reduces the amount of time that you need to invest to administer a DBMS. However, these services can also limit the range of custom administration tasks that you can perform, because manually performing some tasks might risk compromising the way in which the service runs. If you need more control than Azure Data Services allow, you can install your database management system on a virtual machine that runs in Azure.</p>
<p>Apart from reducing the administrative workload, Azure Data Services ensure that your databases are available for at least 99.99% of the time. Additionally, these services are designed to be <em>always on</em>. This means that you can’t shut down a database and restart it later.</p>
<h3 id="sql-server-on-azure-virtual-machines">SQL Server on Azure virtual machines</h3>
<p>Microsoft SQL Server is a popular relational DBMS. It has a long history, and has features that provide database management to organizations of all sizes.</p>
<h4 id="what-is-sql-server-on-azure-virtual-machines">What is SQL Server on Azure Virtual Machines?</h4>
<p>SQL Server on Virtual Machines enables you to use full versions of SQL Server in the Cloud without having to manage any on-premises hardware. This is an example of the IaaS approach.</p>
<p>SQL Server running on an Azure virtual machine effectively replicates the database running on real on-premises hardware. Migrating from the system running on-premises to an Azure virtual machine is no different than moving the databases from one on-premises server to another.</p>
<p>This approach is suitable for migrations and applications requiring access to operating system features that might be unsupported at the PaaS level. SQL virtual machines are <em>lift-and-shift</em> ready for existing applications that require fast migration to the cloud with minimal changes. The term <em>lift-and-shift</em> refers to the way in which you can move a database directly from an on-premises server to an Azure virtual machine without requiring that you make any changes to it.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-relational-data-offerings/media/3-sql-server-azure-virtual-machine.png" alt="Diagram illustrating the lift-and-shift approach to migrating SQL Server running on-premises to a virtual machine in Azure"></p>
<h3 id="use-cases">Use cases</h3>
<p>This approach is optimized for migrating existing applications to Azure, or extending existing on-premises applications to the cloud in hybrid deployments. A <em>hybrid deployment</em> is a system where part of the operation runs on-premises, and part in the cloud.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-relational-data-offerings/media/3-hybrid-solution.png" alt="Image depicting a hybrid deployment"><br>
You can use SQL Server in a virtual machine to develop and test traditional SQL Server applications.</p>
<p>These capabilities enable you to:</p>
<ul>
<li>Create rapid development and test scenarios when you do not want to buy on-premises non-production SQL Server hardware.</li>
<li>Become lift-and-shift ready for existing applications that require fast migration to the cloud with minimal changes or no changes.</li>
<li>Scale up the platform on which SQL Server is running, by allocating more memory, CPU power, and disk space to the virtual machine.</li>
</ul>
<h5 id="business-benefits">Business benefits</h5>
<p>Running SQL Server on virtual machines allows you to meet unique and diverse business needs through a combination of on-premises and cloud-hosted deployments, while using the same set of server products, development tools, and expertise across these environments.</p>
<h3 id="azure-sql-database">Azure SQL Database</h3>
<h4 id="what-is-azure-sql-database">What is Azure SQL Database?</h4>
<p>Azure SQL Database is a PaaS offering from Microsoft. You create a managed database server in the cloud, and then deploy your databases on this server. A SQL Database server is a logical construct that acts as a central administrative point for multiple single or pooled databases, logins, firewall rules, auditing rules, threat detection policies, and failover groups. Azure SQL Database is available with several options: <em>Single Database</em>, <em>Elastic Pool</em>, and <em>Managed Instance</em>.</p>
<h5 id="single-database">Single Database</h5>
<p>This option enables you to quickly set up and run a single SQL Server database. You create and run a database server in the cloud, and you access your database through this server.</p>
<ul>
<li>Microsoft manages the server, so all you have to do is configure the database, create your tables, and populate them with your data.</li>
<li>You can scale the database if you need additional storage space, memory, or processing power.</li>
<li>By default, resources are pre-allocated, and you’re charged per hour for the resources you’ve requested.</li>
<li>You can also specify a <em>serverless</em> configuration. In this configuration, Microsoft creates its own server, which might be shared by a number of databases belonging to other Azure subscribers.</li>
</ul>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-relational-data-offerings/media/4-single-database.png" alt="Image showing the resources managed by Azure SQL Database using the Single Database deployment option"></p>
<h5 id="elastic-pool">Elastic Pool</h5>
<p>This option is similar to <em>Single Database</em>, except that by default multiple databases can share the same resources, such as memory, data storage space, and processing power through multiple-tenancy. The resources are referred to as a <em>pool</em>. This model is useful if you have databases with resource requirements that vary over time, and can help you to reduce costs.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-relational-data-offerings/media/4-elastic-pool.png" alt="Image showing the resources managed by Azure SQL Database using the Elastic Pool deployment option"></p>
<h4 id="use-cases-1">Use cases</h4>
<p>Azure SQL Database gives you the best option for low cost with minimal administration. It is not fully compatible with on-premises SQL Server installations. It is often used in new cloud projects where the application design can accommodate any required changes to your applications.<br>
You can use the Data Migration Assistant to detect compatibility issues with your databases that can impact database functionality in Azure SQL Database.</p>
<p>Azure SQL Database is often used for:</p>
<ul>
<li>Modern cloud applications that need to use the latest stable SQL Server features.</li>
<li>Applications that require high availability.</li>
<li>Systems with a variable load, that need the database server to scale up and down quickly.</li>
</ul>
<h4 id="business-benefits-1">Business benefits</h4>
<ul>
<li>automatical update</li>
<li>scalability</li>
<li>high availability guarantees, to ensure that your databases are available at least 99.99% of the time.</li>
<li>Advanced threat protection provides advanced security capabilities, such as vulnerability assessments, to help detect and remediate potential security problems with your databases.</li>
<li>Auditing tracks database events and writes them to an audit log in your Azure storage account. Auditing can help you maintain regulatory compliance, understand database activity, and gain insight into discrepancies and anomalies that might indicate business concerns or suspected security violations.</li>
<li>SQL Database helps secure your data by providing encryption. For data in motion, it uses Transport Layer Security.</li>
</ul>
<h3 id="azure-sql-database-managed-instance">Azure SQL Database Managed Instance</h3>
<h4 id="what-is-azure-sql-database-managed-instance">What is Azure SQL Database managed instance?</h4>
<p>The Single Database and Elastic Pool options restrict some of the administrative features available to SQL Server. Managed instance effectively runs a fully controllable instance of SQL Server in the cloud. You can install multiple databases on the same instance. You have complete control over this instance, much as you would for an on-premises server. The Managed instance service automates backups, software patching, database monitoring, and other general tasks, but you have full control over security and resource allocation for your databases.</p>
<p>Managed instances depend on other Azure services such as Azure Storage for backups, Azure Event Hubs for telemetry, Azure Active Directory for authentication, Azure Key Vault for Transparent Data Encryption (TDE) and a couple of Azure platform services that provide security and supportability features.</p>
<p>All communications are encrypted and signed using certificates.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-relational-data-offerings/media/5-azure-sql-database-graphic.png" alt="Image showing a comparison on between managed instance, Single Database, and Elastic Database"></p>
<h4 id="use-cases-2">Use cases</h4>
<p>Consider Azure SQL Database managed instance if you want to <em>lift-and-shift</em> an on-premises SQL Server instance and all its databases to the cloud, without incurring the management overhead of running SQL Server on a virtual machine.</p>
<p>If your system uses features such as linked servers, Service Broker (a message processing system that can be used to distribute work across servers), or Database Mail (which enables your database to send email messages to users), then you should use managed instance. To check compatibility with an existing on-premises system, you can install <a href="https://www.microsoft.com/download/details.aspx?id=53595">Data Migration Assistant (DMA)</a>.</p>
<h4 id="business-benefits-2">Business benefits</h4>
<p>SQL Database managed instance provides all the management and security benefits available when using Single Database and Elastic Pool. Managed instance deployment enables a system administrator to spend less time on administrative tasks because the SQL Database service either performs them for you or greatly simplifies those tasks.</p>
<p>Managed instance has near 100% compatibility with SQL Server Enterprise Edition, running on-premises.</p>
<h3 id="postgresql-mariadb-and-mysql">PostgreSQL, MariaDB, and MySQL</h3>
<p>The primary reason for these services is to enable organizations running PostgreSQL, MySQL, or MariaDB to move to Azure quickly, without making wholesale changes to their applications.</p>
<h4 id="what-are-mysql-mariadb-and-postgresql">What are MySQL, MariaDB, and PostgreSQL</h4>
<p>MySQL started life as a simple-to-use open-source database management system. It is the leading open source relational database for <em>Linux, Apache, MySQL, and PHP</em> (LAMP) stack apps.</p>
<p>MariaDB is a newer database management system, created by the original developers of MySQL. The database engine has since been rewritten and optimized to improve performance.</p>
<p>PostgreSQL is a hybrid relational-object database. You can store data in relational tables, but a PostgreSQL database also enables you to store custom data types, with their own non-relational properties. PostgreSQL has its own query language called <em>pgsql</em>.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-relational-data-offerings/media/6-mysql-mariadb-postgresql.png" alt="Advantages of MySQL, MariaDB, and PostgreSQL"></p>
<h4 id="what-is-azure-database-for-mysql">What is Azure Database for MySQL?</h4>
<p>Azure Database for MySQL is a PaaS implementation of MySQL in the Azure cloud, based on the MySQL Community Edition.</p>
<h4 id="what-is-azure-database-for-mariadb">What is Azure Database for MariaDB?</h4>
<p>Azure Database for MariaDB is an implementation of the MariaDB database management system adapted to run in Azure. It’s based on the MariaDB Community Edition.</p>
<h4 id="what-is-azure-database-for-postgresql">What is Azure Database for PostgreSQL?</h4>
<p>If you prefer PostgreSQL, you can choose Azure Database for PostgreSQL to run a PaaS implementation of PostgreSQL in the Azure Cloud.</p>
<p>Some features of on-premises PostgreSQL databases are not available in Azure Database for PostgreSQL. These features are mainly concerned with the extensions that users can add to a database to perform specialized tasks, such as writing stored procedures in various programming languages (other than pgsql, which is available), and interacting directly with the operating system.</p>
<h5 id="azure-database-for-postgresql-single-server">Azure Database for PostgreSQL single-server</h5>
<p>The single-server deployment option for PostgreSQL provides similar benefits as Azure Database for MySQL. You choose from three pricing tiers: Basic, General Purpose, and Memory Optimized. Each tier supports different numbers of CPUs, memory, and storage sizes—you select one based on the load you expect to support.</p>
<h5 id="azure-database-for-postgresql-hyperscale-citus">Azure Database for PostgreSQL Hyperscale (Citus)</h5>
<p>Hyperscale (Citus) is a deployment option that scales queries across multiple server nodes to support large database loads. Your database is split across nodes. Data is split into chunks based on the value of a partition key or sharding key. Consider using this deployment option for the largest database PostgreSQL deployments in the Azure Cloud.</p>
<h5 id="benefits-of-azure-database-for-postgresql">Benefits of Azure Database for PostgreSQL</h5>
<p>Azure Database for PostgreSQL is a highly available service. It contains built-in failure detection and failover mechanisms.</p>
<p>Users of PostgreSQL will be familiar with the <strong>pgAdmin</strong> tool, which you can use to manage and monitor a PostgreSQL database. You can continue to use this tool to connect to Azure Database for PostgreSQL. However, some server-focused functionality, such as performing server backup and restore, are not available because the server is managed and maintained by Microsoft.</p>
<p>Azure Database for PostgreSQL servers records information about the queries run against databases on the server, and saves them in a database named <em>azure_sys</em>.</p>
<h4 id="migrate-data-to-azure">Migrate data to Azure</h4>
<p>If you have existing MySQL, MariaDB, or PostgreSQL databases running on premises, and you want to move the data to a database running the corresponding data services in Azure, you can use the <a href="https://docs.microsoft.com/en-us/azure/dms/tutorial-postgresql-azure-postgresql-online">Azure Database Migration Service (DMS)</a>.</p>
<h2 id="explore-provisioning-and-deploying-relational-database-services-in-azure">Explore provisioning and deploying relational database services in Azure</h2>
<h3 id="describe-provisioning-relational-data-services">Describe provisioning relational data services</h3>
<h4 id="what-is-provisioning">What is provisioning?</h4>
<p>Provisioning is the act of running series of tasks that a service provider, such as Azure SQL Database, performs to create and configure a service. Behind the scenes, the service provider will set up the various resources (disks, memory, CPUs, networks, and so on) required to run the service. How the service provider provisions resources is opaque, and you don’t need to be concerned with how this process works.<br>
All you do is specify parameters that determine the size of the resources required (how much disk space, memory, computing power, and network bandwidth). These parameters are determined by estimating the size of the workload that you intend to run using the service.<br>
In many cases, you can modify these parameters after the service has been created, perhaps increasing the amount of storage space or memory if the workload is greater than you initially anticipated. The act of increasing (or decreasing) the resources used by a service is called <em>scaling</em>.</p>
<p>Azure provides several tools you can use to provision services:</p>
<ul>
<li><em>The Azure portal</em>.</li>
<li><em>The Azure command-line interface (CLI)</em></li>
<li><em>Azure PowerShell</em>.</li>
<li><em>Azure Resource Manager templates</em>.</li>
</ul>
<h3 id="describe-provisioning-postgresql-and-mysql">Describe provisioning PostgreSQL and MySQL</h3>
<h4 id="how-to-provision-azure-database-for-postgresql-and-azure-database-for-mysql">How to provision Azure Database for PostgreSQL and Azure Database for MySQL</h4>
<p>As with Azure SQL Database, you can provision a PostgreSQL or MySQL database interactively using the Azure portal. The processes for provisioning Azure Database for PostgreSQL and Azure Database for MySQL are very similar.<br>
PostgreSQL also gives you the hyperscale option, which supports ultra-high performance workloads. The hyperscale deployment option supports:</p>
<ul>
<li>Horizontal scaling across multiple machines.</li>
<li>Query parallelization across these servers. The service can split resource intensive queries into pieces which can be run in parallel on the different servers. The results from each server are aggregated back together to produce a final result. This mechanism can deliver faster responses on queries over large datasets.</li>
<li>Excellent support for multi-tenant applications, real time operational analytics, and high throughput transactional workloads</li>
</ul>
<p>You can select between three pricing tiers, each of which is designed to support different workloads:</p>
<ul>
<li>
<p><strong>Basic</strong>. This tier is suitable for workloads that require light compute and I/O performance. Examples include servers used for development or testing or small-scale, infrequently used applications.</p>
</li>
<li>
<p><strong>General Purpose</strong>. Use this pricing tier for business workloads that require balanced compute and memory with scalable I/O throughput. Examples include servers for hosting web and mobile apps and other enterprise applications.</p>
</li>
<li>
<p><strong>Memory Optimized</strong> This tier supports high-performance database workloads that require in-memory performance for faster transaction processing and higher concurrency. Examples include servers for processing real-time data and high-performance transactional or analytical apps.</p>
</li>
</ul>
<p>The <strong>Configure</strong> page displays the performance that General Purpose and Memory Optimized configurations provide in terms of <strong>IOPS</strong>. IOPS is an acronym for <em>Input/Output Operations per seconds</em>, and is a measure of the read and write capacity available using the configured resources.</p>
<h3 id="describe-configuring-relational-data-services">Describe configuring relational data services</h3>
<p>After you’ve provisioned a resource, you’ll often need to configure it to meet the needs of your applications and environment. For example, you might need to set up network access, or open a firewall port to enable your applications to connect to the resource.</p>
<h4 id="configure-connectivity-and-firewalls">Configure connectivity and firewalls</h4>
<p>The default connectivity for Azure relational data services is to disable access to the world.</p>
<h5 id="configure-connectivity-to-virtual-networks-and-on-premises-computers">Configure connectivity to virtual networks and on-premises computers</h5>
<p>To enable connectivity, use the <strong>Firewalls and virtual networks</strong> page for a service. To enable connectivity, choose <strong>Selected networks</strong>. In the <strong>Virtual networks</strong> section, you can specify which virtual networks are allowed to route traffic to the service.</p>
<p>Azure SQL Database communicates over port 1433.</p>
<h5 id="configure-connectivity-from-private-endpoints.">Configure connectivity from private endpoints.</h5>
<p><strong>Azure Private Endpoint</strong> is a network interface that connects you privately and securely to a service powered by Azure Private Link. Private Endpoint uses a private IP address from your virtual network, effectively bringing the service into your virtual network.</p>
<h4 id="configure-authentication">Configure authentication</h4>
<p>With Azure Active Directory (AD) authentication, you can centrally manage the identities of database users and other Microsoft services in one central location. Central ID management provides a single place to manage database users and simplifies permission management.</p>
<h4 id="configure-access-control">Configure access control</h4>
<p>Azure AD enables you to specify who, or what, can access your resources. Access control defines what a user or application can do with your resources once they’ve been authenticated. Azure role-based access control (Azure RBAC) helps you manage who has access to Azure resources, and what they can do with those resources.</p>
<p>You control access to resources using Azure RBAC to create role assignments. A role assignment consists of three elements: a security principal, a role definition, and a scope.</p>
<ul>
<li>
<p>A <strong>security principal</strong> is an object that represents a user, group, service principal, or managed identity that is requesting access to Azure resources.</p>
</li>
<li>
<p>A <strong>role definition</strong>, often abbreviated to <em>role</em>, is a collection of permissions. Azure includes several built-in roles that you can use, including:</p>
<ul>
<li>
<p><strong>Owner</strong> - Has full access to all resources including the right to delegate access to others.</p>
</li>
<li>
<p><strong>Contributor</strong> - Can create and manage all types of Azure resources but can’t grant access to others.</p>
</li>
<li>
<p><strong>Reader</strong>- Can view existing Azure resources.</p>
</li>
<li>
<p><strong>User Access Administrator</strong> - Lets you manage user access to Azure resources.</p>
</li>
</ul>
<p>You can also create your own custom roles.</p>
</li>
<li>
<p>A <strong>scope</strong> lists the set of resources that the access applies to.</p>
</li>
</ul>
<p>You add role assignments to a resource in the Azure portal using the <strong>Access control (IAM)</strong> page.</p>
<h4 id="configure-advanced-data-security">Configure advanced data security</h4>
<p>Advanced data security implements threat protection and assessment. Threat protection adds security intelligence to your service. This intelligence monitors the service and detects unusual patterns of activity that could be harmful, or compromise the data managed by the service. Assessment identifies potential security vulnerabilities and recommends actions to mitigate them.</p>
<h3 id="describe-configuring-azure-sql-database-azure-database-for-postgresql-and-azure-database-for-mysql">Describe configuring Azure SQL Database, Azure Database for PostgreSQL, and Azure Database for MySQL</h3>
<h4 id="configure-azure-sql-database">Configure Azure SQL Database</h4>
<p>The overarching principle for network security of the Azure SQL Database offering is to allow only the connection and communication that is necessary to allow the service to operate. All other ports, protocols, and connections are blocked by default. Virtual local area networks (VLANs) and access control lists (ACLs) are used to restrict network communications by source and destination networks, protocols, and port numbers. An ACL contains a list of resources, and the objects (users, computers, and applications) that are allowed to access those resources. Items that implement network-based ACLs include routers and load balancers.</p>
<p>The following steps describe how a connection is established to an Azure SQL database:</p>
<ul>
<li>
<p>Clients connect to a <em>gateway</em> that has a public IP address and listens on port 1433.</p>
</li>
<li>
<p>Depending on the effective connection policy, the gateway either redirects traffic to the database cluster, or acts as a proxy for the database cluster.</p>
</li>
<li>
<p>Inside the database cluster, traffic is forwarded to the appropriate Azure SQL database.</p>
</li>
</ul>
<h5 id="connectivity-from-within-azure">Connectivity from within Azure</h5>
<p>If you’re connecting from within another Azure service, such as a web application running under Azure App Service, your connections have a connection policy of Redirect by default. A policy of Redirect means that after your application establishes a connection to the Azure SQL database through the gateway, all following requests from your application will go directly to the database rather than through the gateway. If connectivity to the database subsequently fails, your application will have to reconnect through the gateway, when it might be directed to a different copy of the database running on another server in the cluster.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-provision-deploy-relational-database-offerings-azure/media/6-redirect.png" alt="Image showing client requests being redirected by the gateway"></p>
<h5 id="connectivity-from-outside-of-azure">Connectivity from outside of Azure</h5>
<p>If you’re connecting from outside Azure, such as an on-premises application, your connections have a connection policy of Proxy by default. A policy of Proxy means the connection is established via the gateway, and all subsequent requests flow through the gateway. Each request could (potentially) be serviced by a different database in the cluster.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-provision-deploy-relational-database-offerings-azure/media/6-proxy.png" alt="Image showing the gateway acting as a proxy for different database servers"></p>
<h5 id="configure-dosguard">Configure DoSGuard</h5>
<p>Denial of service (DoS) attacks are reduced by a SQL Database gateway service called DoSGuard. DoSGuard actively tracks failed logins from IP addresses. If there are multiple failed logins from a specific IP address within a period of time, the IP address is blocked from accessing any resources in the service for a short while.</p>
<h2 id="configure-azure-database-for-postgresql">Configure Azure Database for PostgreSQL</h2>
<p>When you create your Azure Database for PostgreSQL server, a default database named <em>postgres</em> is created. To connect to your database server, you need your full server name and admin sign-in credentials.</p>
<p>Connections to your Azure Database for PostgreSQL server communicate over port 5432.</p>
<h5 id="configure-server-parameters-and-extensions">Configure server parameters and extensions</h5>
<p>A PostgreSQL database server has a number of configuration parameters that you can set. These parameters support fine-tuning of the database, and debugging of code in the database. You can modify these parameters using the <strong>Server parameters</strong> page in the Azure portal. If you’re familiar with PostgreSQL, you’ll find that not all parameters are supported in Azure. Also, not all PostgreSQL extensions are supported in Azure.</p>
<h5 id="configure-read-replicas">Configure read replicas</h5>
<p>You can replicate data from an Azure Database for PostgreSQL server to a read-only server. Azure Database for PostgreSQL supports replication from the master server to up to five replicas. Replicas are updated asynchronously with the PostgreSQL engine native replication technology.</p>
<p>Read replicas help to improve the performance and scale of read-intensive workloads. Read workloads can be isolated to the replicas, while write workloads can be directed to the master.</p>
<p>A common scenario is to have BI and analytical workloads use read replicas as the data source for reporting.</p>
<h4 id="configure-azure-database-for-mysql">Configure Azure Database for MySQL</h4>
<p>In order to connect to the MySQL database you’ve provisioned, you’ll need to enter the connection information. This information includes fully qualified server name and sign-in credentials.</p>
<p>Connections to your Azure Database for MySQL server communicate over port 3306.</p>
<p>By default, SSL connection security is required and enforced on your Azure Database for MySQL server.</p>
<h5 id="configure-server-parameters">Configure server parameters</h5>
<p>Like PostgreSQL, a MySQL database server has a number of configuration parameters that you can set. You can modify these parameters using the <strong>Server parameters</strong> page in the Azure portal.</p>
<h5 id="configure-read-replicas-1">Configure read replicas</h5>
<p>This feature is similar to that available for PostgreSQL. You can create up to five read replicas for a MySQL database.</p>
<h2 id="query-relational-data-in-azure">Query relational data in Azure</h2>
<h3 id="introduction-to-sql">Introduction to SQL</h3>
<p>SQL stands for Structured Query Language. SQL is used to communicate with a relational database. It’s the standard language for relational database management systems.</p>
<p>SQL was originally standardized by the American National Standards Institute (ANSI) in 1986, and by the International Organization for Standardization (ISO) in 1987. Since then, the standard has been extended several times as relational database vendors have added new features to their systems.</p>
<h4 id="understand-sql-dialects">Understand SQL dialects</h4>
<p>You can use SQL statements such as <strong>SELECT</strong>, <strong>INSERT</strong>, <strong>UPDATE</strong>, <strong>DELETE</strong>, <strong>CREATE</strong>, and <strong>DROP</strong> to accomplish almost everything that one needs to do with a database. lthough these SQL statements are part of the SQL standard, many database management systems also have their own additional proprietary extensions to handle the specifics of that database management system. These extensions provide functionality not covered by the SQL standard, and include areas such as security management and programmability.</p>
<p>Some popular dialects of SQL include:</p>
<ul>
<li>
<p><em>Transact-SQL (T-SQL)</em>. This version of SQL is used by Microsoft SQL Server and Azure SQL Database.</p>
</li>
<li>
<p><em>pgSQL</em>. This is the dialect, with extensions implemented in PostgreSQL.</p>
</li>
<li>
<p><em>PL/SQL</em>. This is the dialect used by Oracle. PL/SQL stands for Procedural Language/SQL.</p>
</li>
</ul>
<h4 id="understand-sql-statement-types">Understand SQL statement types</h4>
<p>SQL statements are grouped into two main logical groups, and they are:</p>
<ul>
<li>Data Manipulation Language (DML)</li>
<li>Data Definition Language (DDL)</li>
</ul>
<h5 id="use-dml-statements">Use DML statements</h5>
<p>You use DML statements to manipulate the rows in a relational table.</p>

<table>
<thead>
<tr>
<th>Statement</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>SELECT</td>
<td>Select/Read rows from a table</td>
</tr>
<tr>
<td>INSERT</td>
<td>Insert new rows into a table</td>
</tr>
<tr>
<td>UPDATE</td>
<td>Edit/Update existing rows</td>
</tr>
<tr>
<td>DELETE</td>
<td>Delete existing rows in a table</td>
</tr>
</tbody>
</table><p>The basic form of an <strong>INSERT</strong> statement will insert one row at a time. By default, the <strong>SELECT</strong>, <strong>UPDATE</strong>, and <strong>DELETE</strong> statements are applied to every row in a table. You usually apply a <strong>WHERE</strong> clause with these statements to specify criteria; only rows that match these criteria will be selected, updated, or deleted.</p>
<p>The <strong>FROM</strong> clause specifies the table to use.</p>
<p>If you want to sort the data, you can add an <strong>ORDER BY</strong> clause.</p>
<p>You can also run SELECT statements that retrieve data from multiple tables using a <strong>JOIN</strong> clause.</p>
<p>A number of aggregate functions are available:</p>
<ul>
<li>MIN (which returns the smallest value in a column)</li>
<li>MAX (which returns the largest value in a column)</li>
<li>AVG (which returns the average value, but only if the column contains numeric data),</li>
<li>SUM (which returns the sum of all the values in the column, but only if the column is numeric).</li>
</ul>
<h3 id="use-ddl-statements">Use DDL statements</h3>
<p>You use DDL statements to create, modify, and remove tables and other objects in a database (table, stored procedures, views, and so on).</p>

<table>
<thead>
<tr>
<th>Statement</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>CREATE</td>
<td>Create a new object in the database, such as a table or a view.</td>
</tr>
<tr>
<td>ALTER</td>
<td>Modify the structure of an object. For instance, altering a table to add a new column.</td>
</tr>
<tr>
<td>DROP</td>
<td>Remove an object from the database.</td>
</tr>
<tr>
<td>RENAME</td>
<td>Rename an existing object.</td>
</tr>
</tbody>
</table><p>The following example creates a new database table. The items between the parentheses specify the details of each column, including the name, the data type, whether the column must always contain a value (NOT NULL), and whether the data in the column is used to uniquely identify a row (PRIMARY KEY). Each table should have a primary key, although SQL doesn’t enforce this rule.</p>
<p>Most database management systems support numeric datatypes such as INT (an integer, or whole number), and string types such as VARCHAR (<em>VARCHAR</em> stands for variable length character data).</p>
<h3 id="query-relational-data-in-azure-sql-database">Query relational data in Azure SQL Database</h3>
<h4 id="retrieve-connection-information-for-azure-sql-database">Retrieve connection information for Azure SQL Database</h4>
<p>You can use any of these tools to query data held in Azure SQL Database:</p>
<ul>
<li>The query editor in the Azure portal</li>
<li>The <code>sqlcmd</code> utility from the command line or the Azure Cloud Shell</li>
<li>SQL Server Management Studio</li>
<li>Azure Data Studio</li>
<li>SQL Server Data Tools</li>
</ul>
<p>To use these tools, you first need to establish a connection to the database. Some tools and applications require a connection string that identifies the server, database, account name, and password. You can find this information from the <strong>Overview</strong> page for a database in the Azure portal: select <strong>Show database connection strings</strong>.</p>
<h4 id="use-the-azure-portal-to-query-a-database">Use the Azure portal to query a database</h4>
<p>To access the query editor in the Azure portal, go to the page for your database and select <strong>Query editor</strong>. You’ll be prompted for credentials. You can set the <strong>Authorization type</strong> to <strong>SQL Server authentication</strong> and enter the user name and password that you set up when you created the database. Or you can select <strong>Active Directory password authentication</strong> and provide the credentials of an authorized user in Azure Active Directory.</p>
<h4 id="use-sqlcmd-to-query-a-database">Use SQLCMD to query a database</h4>
<p>The <code>sqlcmd</code> utility runs from the command line and is also available in the Cloud Shell. You specify parameters that identify the server, database, and your credentials.</p>
<pre><code>sqlcmd -S &lt;server&gt;.database.windows.net -d &lt;database&gt; -U &lt;username&gt; -P &lt;password&gt;
</code></pre>
<h4 id="use-azure-data-studio">Use Azure Data Studio</h4>
<p>Azure Data Studio is a graphical utility for creating and running SQL queries from your desktop.</p>
<h4 id="use-sql-server-management-studio">Use SQL Server Management Studio</h4>
<p>SQL Server Management Studio is another tool that you can download and run on your desktop.</p>
<h4 id="use-sql-server-data-tools-in-visual-studio">Use SQL Server Data Tools in Visual Studio</h4>
<p>Visual Studio is a popular development tool for building applications. It’s available in several editions. SQL Server Data Tools are available from the <strong>Tools</strong> menu in Visual Studio.</p>
<h3 id="query-relational-data-in-azure-database-for-postgresql">Query relational data in Azure Database for PostgreSQL</h3>
<p>PostgreSQL provides many tools you can use to connect to a PostgreSQL database and run queries. These tools include the <strong>pgAdmin</strong> graphical user interface, and the <strong>psql</strong> command-line utility.</p>
<h4 id="retrieve-connection-information-for-azure-database-for-postgresql">Retrieve connection information for Azure Database for PostgreSQL</h4>
<p>To connect to a PostgreSQL database, you require the name of the server, and the credentials for an account that has access rights to connect to the server. You can find the server name and the name of the default administrator account on the <strong>Overview</strong> page for the Azure Database for PostgreSQL instance in the Azure portal. Contact your administrator for the password.</p>
<p>As with Azure SQL Database, you must open the PostgreSQL firewall to enable client applications to connect to the service.</p>
<h4 id="use-psql-to-query-a-database">Use psql to query a database</h4>
<p>The <strong>psql</strong> utility is available in the Azure Cloud Shell. You can also run it from a command prompt on your desktop computer, but you must download and install the psql client.</p>
<h4 id="connect-to-postgresql-database-using-azure-data-studio">Connect to PostgreSQL database using Azure Data Studio</h4>
<p>To connect to Azure Database for PostgreSQL from Azure Data Studio, you must first install the PostgreSQL extension.</p>
<h3 id="query-relational-data-in-azure-database-for-mysql">Query relational data in Azure Database for MySQL</h3>
<p>As with PostgreSQL, there are many tools available to connect to MySQL that enable you to create and run scripts of SQL commands. You can use the <strong>mysql</strong> command-line utility, which is also available in the Azure Cloud Shell, or you can use graphical tools from the desktop such as MySQL Workbench.</p>
<p>Currently there are no extensions available for connecting to MySQL from Azure Data Studio.</p>
<h4 id="retrieve-connection-information-for-azure-database-for-mysql">Retrieve connection information for Azure Database for MySQL</h4>
<p>Like SQL Database and PostgreSQL, you require the name of the server, and the credentials for an account that has access rights to connect to the server. You can find the server name and the name of the default administrator account on the <strong>Overview</strong> page for the Azure Database for MySQL instance in the Azure portal. Contact your administrator for the password.</p>
<p>You must also open the MySQL firewall to enable client applications to connect to the service.</p>
<h4 id="use-mysql-workbench-to-query-a-database">Use MySQL Workbench to query a database</h4>
<p>You can download and install MySQL Workbench from the MySQL Community Downloads page.</p>
<h2 id="explore-non-relational-data-offerings-in-azure">Explore non-relational data offerings in Azure</h2>
<h3 id="explore-azure-table-storage">Explore Azure Table storage</h3>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-non-relational-data-offerings-azure/media/2-key-value-store.png" alt="Image showing the structure of a key-value store"></p>
<h4 id="what-is-azure-table-storage">What is Azure Table Storage?</h4>
<p>Azure Table Storage is a scalable key-value store held in the cloud.</p>
<p>Azure Table Storage implements the NoSQL key-value model. In this model, the data for an item is stored as a set of fields, and the item is identified by a unique key.</p>
<p>An Azure table enables you to store semi-structured data. All rows in a table must have a key, but apart from that the columns in each row can vary. Unlike traditional relational databases, Azure Table Storage tables have no concept of relationships, stored procedures, secondary indexes, or foreign keys. Data will usually be denormalized, with each row holding the entire data for a logical entity.</p>
<p>Using Azure Table Storage can provide much faster access to the details of a customer in some scenarios because the data is available in a single row, without requiring that you perform joins across relationships.</p>
<p>To help ensure fast access, Azure Table Storage splits a table into partitions. Partitioning is a mechanism for grouping related rows, based on a common property or <em>partition key</em>. Rows that share the same partition key will be stored together. Partitioning not only helps to organize data, it can also improve scalability and performance:</p>
<ul>
<li>
<p>Partitions are independent from each other, and can grow or shrink as rows are added to, or removed from, a partition. A table can contain any number of partitions.</p>
</li>
<li>
<p>When you search for data, you can include the partition key in the search criteria. This helps to narrow down the volume of data to be examined, and improves performance by reducing the amount of I/O (reads and writes) needed to locate the data.</p>
</li>
</ul>
<p>The key in an Azure Table Storage table comprises two elements; the partition key that identifies the partition containing the row (as described above), and a row key that is unique to each row in the same partition. Items in the same partition are stored in row key order.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-non-relational-data-offerings-azure/media/2-table-partitions.png" alt="Image showing how a table is organized into a set of partitions"><br>
This scheme enables an application to quickly perform <em>Point queries</em> that identify a single row, and <em>Range queries</em> that fetch a contiguous block of rows in a partition.</p>
<h4 id="use-cases-and-management-benefits-of-using-azure-table-storage">Use cases and management benefits of using Azure Table Storage</h4>
<p>The primary advantages of using Azure Table Storage tables over other ways of storing data include:</p>
<ul>
<li>It’s simpler to scale. It takes the same time to insert data in an empty table, or a table with billions of entries. An Azure storage account can hold up to 5 PB of data.</li>
<li>A table can hold semi-structured data</li>
<li>There’s no need to map and maintain the complex relationships typically required by a normalized relational database.</li>
<li>Row insertion is fast</li>
<li>Data retrieval is fast, if you specify the partition and row keys as query criteria</li>
</ul>
<p>There are disadvantages to storing data this way though, including:</p>
<ul>
<li>Consistency needs to be given consideration as transactional updates across multiple entities aren’t guaranteed</li>
<li>There’s no referential integrity; any relationships between rows need to be maintained externally to the table</li>
<li>It’s difficult to filter and sort on non-key data. Queries that search based on non-key fields could result in full table scans</li>
</ul>
<p>Azure Table Storage is an excellent mechanism for:</p>
<ul>
<li>Storing TBs of structured data capable of serving web scale applications.</li>
<li>Storing datasets that don’t require complex joins, foreign keys, or stored procedures, and that can be denormalized for fast access.</li>
<li>Capturing event logging and performance monitoring data.</li>
</ul>
<p>Azure Table Storage is intended to support very large volumes of data, up to several hundred TBs in size.</p>
<p>Azure Table Storage provides high-availability guarantees in a single region. The data for each table is replicated three times within an Azure region. For increased availability, but at additional cost, you can create tables in geo-redundant storage.</p>
<p>You can configure security and role-based access control to ensure that only the people or applications that need to see your data can actually retrieve it.</p>
<h3 id="explore-azure-blob-storage">Explore Azure Blob storage</h3>
<h4 id="what-is-azure-blob-storage">What is Azure Blob storage?</h4>
<p>Azure Blob storage is a service that enables you to store massive amounts of unstructured data, or <em>blobs</em>, in the cloud. Like Azure Table storage, you create blobs using an Azure storage account.</p>
<p>Microsoft Azure virtual machines use blob storage for holding virtual machine disk images. These objects can be several hundreds of GB in size.</p>
<p>Azure currently supports three different types of blob:</p>
<ul>
<li>
<p><em>Block blobs</em>. A block blob is handled as a set of blocks. Each block can vary in size, up to 100 MB. A block blob can contain up to 50,000 blocks, giving a maximum size of over 4.7 TB. The block is the smallest amount of data that can be read or written as an individual unit. Block blobs are best used to store discrete, large, binary objects that change infrequently.</p>
</li>
<li>
<p><em>Page blobs</em>. A page blob is organized as a collection of fixed size 512-byte pages. A page blob is optimized to support random read and write operations; you can fetch and store data for a single page if necessary. A page blob can hold up to 8 TB of data. Azure uses page blobs to implement virtual disk storage for virtual machines.</p>
</li>
<li>
<p><em>Append blobs</em>. An append blob is a block blob optimized to support append operations. You can only add blocks to the end of an append blob; updating or deleting existing blocks isn’t supported. Each block can vary in size, up to 4 MB. The maximum size of an append blob is just over 195 GB.</p>
</li>
</ul>
<p>Inside an Azure storage account, you create blobs inside <em>containers</em>. A container provides a convenient way of grouping related blobs together, and you can organize blobs in a hierarchy of folders, similar to files in a file system on disk. You control who can read and write blobs inside a container at the container level.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-non-relational-data-offerings-azure/media/3-container.png" alt="Image showing how blobs are organized by containers"><br>
Blob storage provides three access tiers, which help to balance access latency and storage cost:</p>
<ul>
<li>The <em>Hot</em> tier is the default. You use this tier for blobs that are accessed frequently.</li>
<li>The <em>Cool</em> tier. This tier has lower performance and incurs reduced storage charges compared to the Hot tier.</li>
<li>The <em>Archive</em> tier. This tier provides the lowest storage cost, but with increased latency. The Archive tier is intended for historical data that mustn’t be lost, but is required only rarely. For the Archive tier, it can take hours for the data to become available. To retrieve a blob from the Archive tier, you must change the access tier to Hot or Cool. The blob will then be <em>rehydrated</em>.</li>
</ul>
<p>You can create lifecycle management policies for blobs in a storage account. A lifecycle management policy can automatically move a blob from Hot to Cool, and then to the Archive tier, as it ages and is used less frequently.</p>
<h4 id="use-cases-and-management-benefits-of-using-azure-blob-storage">Use cases and management benefits of using Azure Blob Storage</h4>
<p>Common uses of Azure Blob Storage include:</p>
<ul>
<li>Serving images or documents directly to a browser, in the form of a static website</li>
<li>Storing files for distributed access</li>
<li>Streaming video and audio</li>
<li>Storing data for backup and restore, disaster recovery, and archiving</li>
<li>Storing data for analysis by an on-premises or Azure-hosted service</li>
</ul>
<p>To ensure availability, Azure Blob storage provides redundancy. Blobs are always replicated three times in the region in which you created your account, but you can also select geo-redundancy, which replicates your data in a second region (at additional cost).</p>
<p>Other features available with Azure Blob storage include:</p>
<ul>
<li>
<p><em>Versioning</em>. You can maintain and restore earlier versions of a blob.</p>
</li>
<li>
<p><em>Soft delete</em>. This feature enables you to recover a blob that has been removed or overwritten, by accident or otherwise.</p>
</li>
<li>
<p><em>Snapshots</em>. A snapshot is a read-only version of a blob at a particular point in time.</p>
</li>
<li>
<p><em>Change Feed</em>. The change feed for a blob provides an ordered, read-only, record of the updates made to a blob.</p>
</li>
</ul>
<h3 id="explore-azure-file-storage">Explore Azure File storage</h3>
<h4 id="what-is-azure-file-storage">What is Azure File Storage?</h4>
<p>Azure File Storage enables you to create files shares in the cloud, and access these file shares from anywhere with an internet connection. Azure File Storage exposes file shares using the Server Message Block 3.0 (SMB) protocol. This is the same file sharing protocol used by many existing on-premises applications. These applications should continue to work unchanged if you migrate your file shares to the cloud. You can control access to shares in Azure File Storage using authentication and authorization services available through Azure Active Directory Domain Services.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-non-relational-data-offerings-azure/media/4-file-shares.png" alt="Image showing the relationships between a storage account, file shares, applications using the file shares, and Azure Active Directory Domain Services"><br>
You create Azure File storage in a storage account. Azure File Storage enables you to share up to 100 TB of data in a single storage account. This data can be distributed across any number of file shares in the account. The maximum size of a single file is 1 TB, but you can set quotas to limit the size of each share below this figure.</p>
<h4 id="use-cases-and-management-benefits-of-using-azure-file-storage">Use cases and management benefits of using Azure File Storage</h4>
<p>Azure File Storage is designed to support many scenarios, including the following:</p>
<ul>
<li>
<p>Migrate existing applications to the cloud.</p>
</li>
<li>
<p>Share server data across on-premises and cloud.</p>
</li>
<li>
<p>Integrate modern applications with Azure File Storage.</p>
<p>By leveraging the modern REST API that Azure File Storage implements in addition to SMB 3.0, you can integrate legacy applications with modern cloud applications, or develop new file or file share-based applications.</p>
</li>
<li>
<p>Simplify hosting High Availability (HA) workload data.</p>
</li>
</ul>
<p>Don’t use Azure File Storage for files that can be written by multiple concurrent processes simultaneously.</p>
<p>Azure Files Storage is a fully managed service. Your shared data is replicated locally within a region, but can also be geo-replicated to a second region.</p>
<p>All data is encrypted at rest, and you can enable encryption for data in-transit between Azure File Storage and your applications.</p>
<h3 id="explore-azure-cosmos-db">Explore Azure Cosmos DB</h3>
<h4 id="what-is-azure-cosmos-db">What is Azure Cosmos DB?</h4>
<p>Azure Cosmos DB is a multi-model NoSQL database management system. Cosmos DB manages data as a partitioned set of documents. A document is a collection of fields, identified by a key. The fields in each document can vary, and a field can contain child documents. Many document databases use JSON (JavaScript Object Notation) to represent the document structure.</p>
<p>A document can hold up to 2 MB of data, including small binary objects.</p>
<p>The APIs that Cosmos DB currently supports include:</p>
<ul>
<li><em>SQL API</em>.</li>
<li><em>Table API</em>. This interface enables you to use the Azure Table Storage API to store and retrieve documents.</li>
<li><em>MongoDB API</em>.</li>
<li><em>Cassandra API</em>. Cassandra is a column family database management system.</li>
<li><em>Gremlin API</em>. The Gremlin API implements a graph database interface to Cosmos DB. A graph is a collection of data objects and directed relationships. Data is still held as a set of documents in Cosmos DB, but the Gremlin API enables you to perform graph queries over data.</li>
</ul>
<p>The primary purpose of the Table, MongoDB, Cassandra, and Gremlin APIs is to support existing applications. If you are building a new application and database, you should use the SQL API.</p>
<p>Documents in a Cosmos DB database are organized into containers. The documents in a container are grouped together into partitions. A partition holds a set of documents that share a common partition key. You designate one of the fields in your documents as the partition key. You should select a partition key that collects all related documents together.</p>
<p>There’s a superficial similarity between a Cosmos DB container and a table in Azure Table storage: in both cases, data is partitioned and documents (rows in a table) are identified by a unique ID within a partition. However, the similarity ends there. Unlike Azure Table storage, documents in a Cosmos DB partition aren’t sorted by ID. Instead, Cosmos DB maintains a separate index. This index contains not only the document IDs, but also tracks the value of every other field in each document.</p>
<h4 id="use-cases-and-management-benefits-of-using-azure-cosmos-db">Use cases and management benefits of using Azure Cosmos DB</h4>
<p>Cosmos DB is a highly scalable database management system. Cosmos DB automatically allocates space in a container for your partitions, and each partition can grow up to 10 GB in size. Indexes are created and maintained automatically.</p>
<p>To ensure availability, all databases are replicated within a single region. This replication is transparent, and failover from a failed replica is automatic. Cosmos DB guarantees 99.99% high availability. Additionally, you can choose to replicate data across regions, at additional cost. All replicas are synchronized, although there may be a small window while updates are transmitted and applied. The multi-master replication protocol supports five well-defined consistency choices - strong, bounded staleness, session, consistent prefix, and eventual.</p>
<p>Cosmos DB guarantees less than 10-ms latencies for both reads (indexed) and writes at the 99th percentile, all around the world.</p>
<p>Cosmos DB is certified for a wide array of compliance standards. Additionally, all data in Cosmos DB is encrypted at rest and in motion.</p>
<p>Cosmos DB is highly suitable for the following scenarios:</p>
<ul>
<li><em>IoT and telematics</em>. These systems typically ingest large amounts of data in frequent bursts of activity.</li>
<li><em>Retail and marketing</em>.</li>
<li><em>Gaming</em>. The database tier is a crucial component of gaming applications. Games often require single-millisecond latencies for reads and write to provide an engaging in-game experience</li>
<li><em>Web and mobile applications</em>.</li>
</ul>
<h2 id="explore-provisioning-and-deploying-non-relational-data-services-in-azure">Explore provisioning and deploying non-relational data services in Azure</h2>
<h3 id="provision-azure-cosmos-db">Provision Azure Cosmos DB</h3>
<p>In Cosmos DB, you organize your data as a collection of documents stored in containers. Containers are held in a database. A database runs in the context of a Cosmos DB account. You must create the account before you can set up any databases.</p>
<h4 id="how-to-provision-a-cosmos-db-account">How to provision a Cosmos DB account</h4>
<p>You can provision a Cosmos DB account interactively using the Azure portal, or you can perform this task programmatically through the Azure CLI, Azure PowerShell, or an Azure Resource Manager template.</p>
<p>Azure CLI</p>
<pre><code>## Azure CLI

az cosmosdb create \
  --subscription &lt;your-subscription&gt; \
  --resource-group &lt;resource-group-name&gt; \
  --name &lt;cosmosdb-account-name&gt; \
  --locations regionName=eastus failoverPriority=0 \
  --locations regionName=westus failoverPriority=1 \
  --enable-multiple-write-locations
</code></pre>
<p>PowerShell</p>
<pre><code>## Azure PowerShell

New-AzCosmosDBAccount `
  -ResourceGroupName "&lt;resource-group-name&gt;" `
  -Name "&lt;cosmosbd-account-name&gt;" `
  -Location @("West US", "East US") `
  -EnableMultipleWriteLocations
</code></pre>
<h4 id="how-to-create-a-database-and-a-container">How to create a database and a container</h4>
<p>Databases and containers are the primary resource consumers. Resources are allocated in terms of the storage space required to hold your databases and containers, and the processing power required to store and retrieve data.</p>
<p>Azure Cosmos DB uses the concept of Request Units per second (RU/s) to manage the performance and cost of databases. This measure abstracts the underlying physical resources that need to be provisioned to support the required performance. Microsoft gives a measure of approximately one RU as the resources required to read a 1-KB document with 10 fields. So a throughput of one RU per second (RU/s) will support an application that reads a single 1-KB document each second. If you underprovision (by specifying too few RU/s), Cosmos DB will start throttling performance. The minimum throughput you can allocate to a database or container is 400 RU/s.</p>
<p>Azure CLI</p>
<pre><code>## Azure CLI - create a database

az cosmosdb sql database create \
  --account-name &lt;cosmos-db-account-name&gt; \
  --name &lt;database-name&gt; \
  --resource-group &lt;resource-group-name&gt; \
  --subscription &lt;your-subscription&gt; \
  --throughput &lt;number-of-RU/s&gt;

## Azure CLI - create a container

az cosmosdb sql container create \
  --account-name &lt;cosmos-db-account-name&gt; \
  --database-name &lt;database-name&gt; \
  --name &lt;container-name&gt; \
  --resource-group &lt;resource-group-name&gt; \
  --partition-key-path &lt;key-field-in-documents&gt;
</code></pre>
<p>PowerShell</p>
<pre><code>## Azure PowerShell - create a database

New-AzCosmosDBSqlDatabase `
    -ResourceGroupName "&lt;resource-group-name&gt;" `
    -AccountName "&lt;cosmos-db-account-name&gt;" `
    -Name "&lt;database-name&gt;" `
    -Throughput &lt;number-of-RU/s&gt;

## Azure PowerShell - create a container

New-AzCosmosDBSqlContainer `
    -ResourceGroupName "&lt;resource-group-name&gt;" `
    -AccountName "&lt;cosmos-db-account-name&gt;" `
    -DatabaseName "&lt;database-name&gt;" `
    -Name "&lt;container-name&gt;" `
    -PartitionKeyKind Hash `
    -PartitionKeyPath "&lt;key-field-in-documents&gt;"
</code></pre>
<h3 id="provision-other-non-relational-data-services">Provision other non-relational data services</h3>
<p>This unit describes how to provision Data Lake storage, Blob storage, and File Storage. As with Cosmos DB, you can provision these services using the Azure portal, the Azure CLI, Azure PowerShell, and Azure Resource Manager templates. Data Lake storage, Blob storage, and File Storage, all require that you first create an Azure storage account.</p>
<h4 id="how-to-create-a-storage-account">How to create a storage account</h4>
<h5 id="use-the-azure-portal">Use the Azure portal</h5>
<p>Use the <strong>Create storage account</strong> page to set up a new storage account using the Azure portal.</p>
<p><strong>Performance</strong>. This setting has two options:</p>
<ul>
<li><strong>Standard</strong> storage accounts are based on hard disks.</li>
<li><strong>Premium</strong> storage uses solid-state drives, and has much lower latency and better read/write performance than standard storage.</li>
</ul>
<p><strong>Account kind</strong>. Azure storage supports several different types of account:</p>
<ul>
<li><strong>General-purpose v2</strong>. You can use this type of storage account for blobs, files, queues, and tables, and is recommended for most scenarios that require Azure Storage. If you want to provision Azure Data Lake Storage, you should specify this account type.</li>
<li><strong>General-purpose v1</strong>. This is a legacy account type for blobs, files, queues, and tables. Use general-purpose v2 accounts when possible.</li>
<li><strong>BlockBlobStorage</strong>. The type of storage account is only available for premium accounts. You use this account type for block blobs and append blobs.</li>
<li><strong>FileStorage</strong>. This type is also only available for premium accounts. You use it to create files-only storage accounts with premium performance characteristics.</li>
<li><strong>BlobStorage</strong>. This is another legacy account type that can only hold blobs.</li>
</ul>
<p><strong>Replication</strong>. Data in an Azure Storage account is always replicated three times in the region you specify as the primary location for the account.</p>
<ul>
<li><strong>Locally redundant storage (LRS)</strong> copies your data synchronously three times within a single physical location in the region.</li>
<li><strong>Geo-redundant storage (GRS)</strong> copies your data synchronously three times within a single physical location in the primary region using LRS.</li>
<li><strong>Read-access geo-redundant storage (RA-GRS)</strong> replication is an extension of GRS that provides direct read-only access to the data in the secondary location. In contrast, the GRS option doesn’t expose the data in the secondary location, and it’s only used to recover from a failure in the primary location. RA-GRS replication enables you to store a read-only copy of the data close to users that are located in a geographically distant location, helping to reduce read latency times.</li>
<li><strong>Zone redundant storage (ZRS)</strong> Zone-redundant storage replicates your Azure Storage data synchronously across three Azure availability zones in the primary region.</li>
</ul>
<p>To maintain performance, premium storage accounts only support LRS replication. This is because replication is performed synchronously to maintain data integrity. Replicating data to a distant region can increase latency to the point at which any advantages of using premium storage are lost.</p>
<p><strong>Access tier</strong>. This option is only available for standard storage accounts. You can select between <strong>Hot</strong> and <strong>Cool</strong>.</p>
<h5 id="use-the-azure-cli">Use the Azure CLI</h5>
<p>Azure CLI</p>
<pre><code>az storage account create \
  --name &lt;storage-account-name&gt; \
  --resource-group &lt;resource-group&gt; \
  --location &lt;your-location&gt; \
  --sku &lt;sku&gt; \
  --kind &lt;kind&gt; \
  --access-tier &lt;tier&gt;

</code></pre>
<p>The <strong>sku</strong> is combination of the performance tier and replication options. It can be one of Premium_LRS, Premium_ZRS, Standard_GRS, Standard_GZRS, Standard_LRS, Standard_RAGRS, Standard_RAGZRS, or Standard_ZRS.</p>
<p>The <strong>kind</strong> parameter should be one of BlobStorage, BlockBlobStorage, FileStorage, Storage, or StorageV2.</p>
<p>The <strong>access-tier</strong> parameter can either be Cool or Hot.</p>
<h5 id="use-azure-powershell">Use Azure PowerShell</h5>
<pre><code>New-AzStorageAccount `
  -Name "&lt;storage-account-name&gt;" `
  -ResourceGroupName "&lt;resource-group-name&gt;" `
  -Location "&lt;your-location&gt;" `
  -SkuName "&lt;sku&gt;" `
  -Kind "&lt;kind&gt;" `
  -AccessTier "&lt;tier&gt;"
</code></pre>
<h4 id="how-to-provision-data-lake-storage-in-a-storage-account">How to provision Data Lake storage in a storage account</h4>
<p>If you’re provisioning a Data Lake storage, you <strong>must</strong> specify the appropriate configuration settings when you create the storage account. You can’t configure Data Lake storage after the storage account has been set up.</p>
<p>In the Azure portal, on the <strong>Advanced</strong> tab of the <strong>Create storage account</strong> page, in the <strong>Data Lake Storage Gen2</strong> section, select <strong>Enabled</strong> for the <strong>Hierarchical namespace</strong> option.</p>
<p>After the storage account has been created, you can add one or more Data Lake Storage containers to the account.</p>
<h5 id="use-the-azure-cli-1">Use the Azure CLI</h5>
<p>Azure CLI</p>
<pre><code>az storage account create \
  --name &lt;storage-account-name&gt; \
  --resource-group &lt;resource-group&gt; \
  --location &lt;your-location&gt; \
  --sku &lt;sku&gt; \
  --kind &lt;kind&gt; \
  --access-tier &lt;tier&gt; \
  --enable-hierarchical-namespace true

</code></pre>
<h5 id="use-azure-powershell-1">Use Azure PowerShell</h5>
<p>PowerShell</p>
<pre><code>New-AzStorageAccount `
  -Name "&lt;storage-account-name&gt;" `
  -ResourceGroupName "&lt;resource-group-name&gt;" `
  -Location "&lt;your-location&gt;" `
  -SkuName "&lt;sku&gt;" `
  -Kind "&lt;kind&gt;" `
  -AccessTier "&lt;tier&gt;" `
  -EnableHierarchicalNamespace $True

</code></pre>
<h4 id="how-to-provision-blob-storage-in-a-storage-account">How to provision Blob storage in a storage account</h4>
<h5 id="use-the-azure-portal-1">Use the Azure portal</h5>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-provision-deploy-non-relational-data-services-azure/media/4-containers.png" alt="Image of the Overview page for a storage account. The Containers section is highlighted."><br>
The <strong>Containers</strong> page enables you to create and manage containers. You can also specify the access level. By default, data held in a container is only accessible by the container owner. You can set the access level to <strong>Blob</strong> to enable public read access to any blobs created in the container, or <strong>Container</strong> to allow read access to the entire contents of the container, including the ability to list all blobs.</p>
<h5 id="use-the-azure-cli-2">Use the Azure CLI</h5>
<p>Azure CLI</p>
<pre><code>az storage container create \
  --name &lt;container-name&gt; \
  --account-name &lt;storage-account-name&gt; \
  --public-access &lt;access&gt;

</code></pre>
<p>The <strong>public-access</strong> parameter can be <strong>blob</strong>, <strong>container</strong>, or <strong>off</strong> (for private access only).</p>
<h5 id="use-azure-powershell-2">Use Azure PowerShell</h5>
<p>PowerShell</p>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "&lt;resource-group&gt;" `
  -Name "&lt;storage-account-name&gt;" | New-AzStorageContainer `
    -Name "&lt;container-name&gt;" `
    -Permission &lt;permission&gt;

</code></pre>
<p>The <strong>Permission</strong> parameter accepts the values <strong>Blob</strong>, <strong>Container</strong>, or <strong>Off</strong>.</p>
<h4 id="how-to-provision-file-storage-in-a-storage-account">How to provision File storage in a storage account</h4>
<h5 id="use-the-azure-portal-2">Use the Azure portal</h5>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-provision-deploy-non-relational-data-services-azure/media/4-file-shares.png" alt="Image of the Overview page for a storage account. The File shares section is highlighted.">The total size of all files across all file shares in a storage account can’t exceed 5120 GB.</p>
<h5 id="use-the-azure-cli-3">Use the Azure CLI</h5>
<p>Azure CLI</p>
<pre><code>az storage share create \
  --name &lt;share-name&gt; \
  --account-name &lt;storage-account-name&gt;

</code></pre>
<h5 id="use-azure-powershell-3">Use Azure PowerShell</h5>
<p>PowerShell</p>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "&lt;resource-group&gt;" `
  -Name "&lt;storage-account-name&gt;" |New-AzStorageShare `
    -Name "&lt;share-name&gt;"
</code></pre>
<h3 id="describe-configuring-non-relational-data-services">Describe configuring non-relational data services</h3>
<h4 id="configure-connectivity-and-firewalls-1">Configure connectivity and firewalls</h4>
<p>The default connectivity for Azure Cosmos DB and Azure Storage is to enable access to the world at large. You can connect to these services from an on-premises network, the internet, or from within an Azure virtual network. Although this level of access sounds risky, most Azure services mitigate this risk by requiring authentication before granting access.</p>
<h5 id="configure-connectivity-to-virtual-networks-and-on-premises-computers-1">Configure connectivity to virtual networks and on-premises computers</h5>
<p>To restrict connectivity, use the <strong>Networking</strong> page for a service. To limit connectivity, choose <strong>Selected networks</strong>.</p>
<p>In the <strong>Virtual networks</strong> section, you can specify which virtual networks are allowed to route traffic to the service.</p>
<p>If you need to connect to the service from an on-premises computer, in the <strong>Firewall</strong> section, add the IP address of the computer.</p>
<p>The <strong>Exceptions</strong> setting allows you to enable access to any other of your services created in your Azure subscription.</p>
<h5 id="configure-connectivity-from-private-endpoints">Configure connectivity from private endpoints</h5>
<p><strong>Azure Private Endpoint</strong> is a network interface that connects you privately and securely to a service powered by Azure Private Link. Private Endpoint uses a private IP address from your VNet, effectively bringing the service into your VNet.</p>
<h4 id="configure-authentication-1">Configure authentication</h4>
<p>Azure services actually provide two keys, labeled <strong>key1</strong> and <strong>key2</strong>. An application can use either key to connect to the service.</p>
<p>Any user or application that knows the access key for a resource can connect to that resource. However, access keys provide a rather coarse-grained level of authentication. Additionally, if you need to regenerate an access key (after accidental disclosure, for example), you may need to update all applications that connect using that key.</p>
<p>Azure Active Directory (Azure AD) provides superior security and ease of use over access key authorization. You add users and other security principals (such as an application) to a <em>security domain</em> managed by Azure AD.</p>
<h4 id="configure-access-control-1">Configure access control</h4>
<p>Azure AD enables you to specify who, or what, can access your resources. Access control defines what a user or application can do with your resources after they’ve been authenticated. (For further details see RBAC section in relational databases chapter).</p>
<h4 id="configure-security">Configure security</h4>
<p>Apart from authentication and authorization, many services provide additional protection through security.</p>
<p>Security implements threat protection and assessment. Threat protection tracks security incidents and alerts across your service.</p>
<h3 id="configure-azure-cosmos-db-and-azure-storage">Configure Azure Cosmos DB, and Azure Storage</h3>
<h4 id="configure-cosmos-db">Configure Cosmos DB</h4>
<h5 id="configure-replication">Configure replication</h5>
<p>Azure Cosmos DB enables you to replicate the databases and containers in your account across multiple regions. When you initially provision an account, you can specify that you want to copy data to another region. The <strong>Replicate data globally</strong> page enables you to configure replication in more detail. You can replicate to multiple regions, and you select the regions to use.</p>
<p>You can also use this page to configure automatic failover to help ensure high availability.</p>
<p>By default, only the region in which you created the account supports write operations; the replicas are all read-only. However, you can enable multi-region writes. Multi-region writes can cause conflicts though, if applications running in different regions modify the same data. In this case, the most recent write will overwrite changes made earlier when data is replicated, although you can write your own code to apply a different strategy.</p>
<p>Replication is asynchronous, so there’s likely to be a lag between a change made in one region, and that change becoming visible in other regions.</p>
<h3 id="configure-consistency">Configure consistency</h3>
<p>Within a single region, Cosmos DB uses a cluster of servers. This approach helps to improve scalability and availability.</p>
<p>Cosmos DB enables you to specify how inconsistencies should be handled. It provides the following options:</p>
<ul>
<li>
<p><strong>Eventual</strong>. This option is the least consistent. Changes won’t be lost, they’ll appear <em>eventually</em>, but they might not appear immediately. Additionally, if an application makes several changes, some of those changes might be immediately visible, but others might be delayed; changes could appear out of order.</p>
</li>
<li>
<p><strong>Consistent Prefix</strong>. This option ensures that changes will appear in order, although there may be a delay before they become visible.</p>
</li>
<li>
<p><strong>Session</strong>. If an application makes a number of changes, they’ll all be visible to that application, and in order. Other applications may see old data, although any changes will appear in order, as they did for the <strong>Consistent Prefix</strong> option. This form of consistency is sometimes known as <em>read your own writes</em>.</p>
</li>
<li>
<p><strong>Bounded Staleness</strong>. There’s a lag between writing and then reading the updated data. You specify this staleness either as a period of time, or number of previous versions the data will be inconsistent for.</p>
</li>
<li>
<p><strong>Strong</strong>: In this case, all writes are only visible to clients after the changes are confirmed as written successfully to all replicas. This option is unavailable if you need to distribute your data across multiple global regions.</p>
</li>
</ul>
<p>You can change the default consistency for a Cosmos DB account using the <strong>Default consistency</strong> page in the Azure portal. Applications can override the default consistency level for individual read operations. However, they can’t increase the consistency above that specified on this page; they can only decrease it.</p>
<h4 id="configure-storage-accounts">Configure Storage accounts</h4>
<h5 id="general-configuration">General configuration</h5>
<p>The <strong>Configuration</strong> page for a storage account enables you to modify some general settings of the account. You can:</p>
<ul>
<li>
<p>Enable or disable secure communications with the service.</p>
</li>
<li>
<p>Switch the default access tier between Cool and Hot.</p>
</li>
<li>
<p>Change the way in which the account is replicated.</p>
</li>
<li>
<p>Enable or disable integration with Azure Active Directory Domain Services (Azure AD DS) for requests that access file shares.</p>
</li>
</ul>
<h5 id="configure-encryption">Configure encryption</h5>
<p>All data held in an Azure Storage account is automatically encrypted. By default, encryption is performed using keys managed and owned by Microsoft. To use your own keys, add them to Azure Key Vault.</p>
<h5 id="configure-shared-access-signatures">Configure shared access signatures</h5>
<p>You can use shared access signatures (SAS) to grant limited rights to resources in an Azure storage account for a specified time period.</p>
<p>A SAS is a token that an application can use to connect to the resource. The application appends the token to the URL of the resource.</p>
<p>Use the <strong>Shared access signature</strong> page in the Azure portal to generate SAS tokens. The SAS token is encrypted using one of the access keys; you specify which key to use (key1 or key2).</p>
<h2 id="manage-non-relational-data-stores-in-azure">Manage non-relational data stores in Azure</h2>
<h3 id="manage-azure-cosmos-db">Manage Azure Cosmos DB</h3>
<h4 id="perform-data-operations-in-cosmos-db">Perform data operations in Cosmos DB</h4>
<p>Cosmos DB provides several options for uploading data to a Cosmos DB database, and querying that data. You can:</p>
<ul>
<li>Use <strong>Data Explorer</strong> in the Azure portal to run ad-hoc queries. You can also use this tool to load data, but you can only load one document at a time. The data load functionality is primarily aimed at uploading a small number of documents (up to 2 MB in total size) for test purposes, rather than importing large quantities of data.</li>
<li>Use the Cosmos DB Data Migration tool to perform a bulk-load or transfer of data from another data source.</li>
<li>Use Azure Data Factory to import data from another source.</li>
<li>Write a custom application that imports data using the Cosmos DB library.</li>
<li>Create your own application that uses the functions available through the Cosmos DB SQL API client library to store data.</li>
</ul>
<h5 id="load-data-using-the-cosmos-db-data-migration-tool">Load data using the Cosmos DB Data Migration tool</h5>
<p>You can use the Data Migration tool to import data to Azure Cosmos DB from a variety of sources, including:</p>
<ul>
<li>JSON files</li>
<li>MongoDB</li>
<li>SQL Server</li>
<li>CSV files</li>
<li>Azure Table storage</li>
<li>Amazon DynamoDB</li>
<li>HBase</li>
<li>Azure Cosmos containers</li>
</ul>
<h5 id="configure-cosmos-db-to-support-bulk-loading">Configure Cosmos DB to support bulk loading</h5>
<p>If you have a large amount of data, the Data Migration Tool can make use of multiple concurrent threads to batch your data into chunks and load the chunks in parallel. Each thread acts as a separate client connection to the database. Bulk loading can become a write-intensive task. If you’re planning on performing a large data import, you should increase the throughput resources available to the target Cosmos container. If you’re using the Data Migration Tool to create the container as well as populate it, the <strong>Target information</strong> page enables you to specify the throughput resources to allocate. If you’ve already created the container, use the <strong>Scale</strong> settings of the database in the Data Explorer page for your database in the Azure portal to specify the maximum throughput, or set the throughput to <strong>Autoscale</strong>.</p>
<h3 id="query-azure-cosmos-db">Query Azure Cosmos DB</h3>
<p>Although Azure Cosmos DB is described as a NoSQL database management system, the SQL API enables you to run <em>SQL-like</em> queries against Cosmos DB databases. These queries use a syntax similar to that of SQL, but there are some differences. This is because the data in a Cosmos DB is structured as documents rather than tables.</p>
<h4 id="use-the-sql-api-to-query-documents">Use the SQL API to query documents</h4>
<p>A SQL API SELECT query includes the following clauses:</p>
<ol>
<li>
<p><strong>SELECT clause</strong>.</p>
</li>
<li>
<p><strong>FROM clause</strong>.</p>
</li>
<li>
<p><strong>WHERE clause</strong>.</p>
</li>
<li>
<p><strong>ORDER BY clause</strong>.</p>
</li>
</ol>
<p>A query can also contain a <strong>JOIN clause</strong>. In the SQL API, you use JOIN clauses to connect fields in a document with fields in a subdocument that is part of the same document.</p>
<h5 id="understand-supported-operators">Understand supported operators</h5>

<table>
<thead>
<tr>
<th>Type</th>
<th>Operator</th>
</tr>
</thead>
<tbody>
<tr>
<td>Unary</td>
<td>+,-,~, NOT</td>
</tr>
<tr>
<td>Arithmetic</td>
<td>+,-,*,/,%</td>
</tr>
<tr>
<td>Bitwise</td>
<td>|, &amp;, ^, &lt;&lt;, &gt;&gt;, &gt;&gt;&gt;</td>
</tr>
<tr>
<td>Logical</td>
<td>AND, OR</td>
</tr>
<tr>
<td>Comparison</td>
<td>=, !=, &lt;, &gt;, &lt;=, &gt;=, &lt;&gt;</td>
</tr>
<tr>
<td>String (concatenate)</td>
<td>||</td>
</tr>
<tr>
<td>Ternary (if)</td>
<td>?</td>
</tr>
</tbody>
</table><p>The SQL API also supports:</p>
<ul>
<li>
<p>The DISTINCT operator that you use as part of the SELECT clause to eliminate duplicates in the result data.</p>
</li>
<li>
<p>The TOP operator that you can use to retrieve only the first few rows returned by a query that might otherwise generate a large result set.</p>
</li>
<li>
<p>The BETWEEN operation that you use as part of the WHERE clause to define an inclusive range of values. The condition field BETWEEN a AND b is equivalent to the condition <code>field &gt;= a AND field &lt;= b</code>.</p>
</li>
<li>
<p>The IS_DEFINED operator that you can use for detecting whether a specified field exists in a document.</p>
</li>
</ul>
<h5 id="understand-aggregate-functions">Understand aggregate functions</h5>
<p>The SQL API query language supports the following aggregate functions:</p>
<ul>
<li>
<p><strong>COUNT§</strong>.</p>
</li>
<li>
<p><strong>SUM§</strong>.</p>
</li>
<li>
<p><strong>AVG§</strong>.</p>
</li>
<li>
<p><strong>MAX§</strong>.</p>
</li>
<li>
<p><strong>MIN§</strong>.</p>
</li>
</ul>
<p>SQL API query language doesn’t support the GROUP BY clause.</p>
<h4 id="query-documents-with-the-sql-api-using-data-explorer">Query documents with the SQL API using Data Explorer</h4>
<p>You can use Data Explorer in the Azure portal to create and run queries against a Cosmos DB container.</p>
<h3 id="manage-azure-blob-storage">Manage Azure Blob storage</h3>
<h4 id="create-an-azure-storage-container">Create an Azure Storage container</h4>
<p>In an Azure storage account, you store blobs in <em>containers</em>. You create a container in an Azure Storage account.</p>
<h5 id="use-the-azure-portal-3">Use the Azure portal</h5>
<p>In the Azure portal, go to the <strong>Overview</strong> page for your Azure Storage account, and select <strong>Containers</strong>.</p>
<p>On the <strong>Containers</strong> page, select <strong>+ Container</strong>, and provide a name for the new container. You can also specify the public access level. For a container that will be used to hold blobs, the most appropriate access level is <strong>Blob</strong>. This setting supports anonymous read-only access for blobs. However, unauthenticated clients can’t list the blobs in the container. This means they can only download a blob if they know its name and location within the container.</p>
<h5 id="use-the-azure-cli-4">Use the Azure CLI</h5>
<pre><code>az storage container create \
  --name images \
  --account-name contosodata \
  --resource-group contoso-group \
  --public-access blob
</code></pre>
<h5 id="use-azure-powershell-4">Use Azure PowerShell</h5>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "contoso-group" `
  -Name "contosodata" | New-AzStorageContainer `
    -Name "images" `
    -Permission Blob
</code></pre>
<h4 id="upload-a-blob-to-azure-storage">Upload a blob to Azure Storage</h4>
<h5 id="use-the-azure-portal-4">Use the Azure portal</h5>
<p>On the page for the container, in the toolbar, select <strong>Upload</strong>. In the <strong>Upload blob</strong> dialog box, browse to the file container the data to upload. The <strong>Advanced</strong> drop-down section provides options you can modify the default options.</p>
<h5 id="use-the-azure-cli-5">Use the Azure CLI</h5>
<pre><code>az storage blob upload \
  --container-name images \
  --account-name contosodata \
  --file "\data\racer_green_large.gif" \
  --name "bikes\racer_green"
</code></pre>
<pre><code>az storage blob upload-batch \
  --account-name contosodata \
  --source "\data" \
  --pattern "*.gif" \
  --destination "images\bikes"
</code></pre>
<h5 id="use-azure-powershell-5">Use Azure PowerShell</h5>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "contoso-group" `
  -Name "contosodata" | Set-AzStorageBlobContent `
    -Container "images" `
    -File "\data\racer_green_large.gif" `
    -Blob "bikes\racer_green"
</code></pre>
<h4 id="list-the-blobs-in-a-container">List the blobs in a container</h4>
<h5 id="use-the-azure-portal-5">Use the Azure portal</h5>
<p>If you’re using the Azure portal, go to the page for your storage account and select <strong>Containers</strong> under <strong>Blob service</strong>.</p>
<h5 id="use-the-azure-cli-6">Use the Azure CLI</h5>
<pre><code>az storage blob list \
  --account-name contosodata \
  --container-name "images"

</code></pre>
<h5 id="use-azure-powershell-6">Use Azure PowerShell</h5>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "contoso-group" `
  -Name "contosodata" | Get-AzStorageBlob `
    -Container "images"
</code></pre>
<h4 id="download-a-blob-from-a-container">Download a blob from a container</h4>
<h5 id="use-the-azure-portal-6">Use the Azure portal</h5>
<p>Select the blob to view its details. On the details page, select <strong>Download</strong>.</p>
<h5 id="use-the-azure-cli-7">Use the Azure CLI</h5>
<pre><code>az storage blob download \
  --container-name images \
  --account-name contosodata \
  --file "racer_green_large.gif" \
  --name "bikes\racer_green"
</code></pre>
<h5 id="use-azure-powershell-7">Use Azure PowerShell</h5>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "contoso-group" `
  -Name "contosodata" | Get-AzStorageBlobContent `
    -Container "images" `
    -Blob "bikes\racer_green_large.gif" `
    -Destination "racer_green_large.gif" 
</code></pre>
<h4 id="delete-a-blob-from-a-container">Delete a blob from a container</h4>
<p>Deleting a blob can reclaim the resources used in the storage container. However, if you’ve enabled the soft delete option for the storage account, the blob is hidden rather than removed, and you can restore it later.<br>
If you created the storage account with support for hierarchical namespaces (for Data Lake Storage), the soft delete option isn’t available.</p>
<h5 id="use-the-azure-portal-7">Use the Azure portal</h5>
<p>Select the blob to view its details. On the details page, select <strong>Delete</strong>.</p>
<h5 id="use-the-azure-cli-8">Use the Azure CLI</h5>
<pre><code>az storage blob delete \
  --account-name contosodata \
  --container-name "images" \
  --name "bikes\racer_green"
</code></pre>
<h5 id="use-azure-powershell-8">Use Azure PowerShell</h5>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "contoso-group" `
  -Name "contosodata" | Remove-AzStorageBlob `
    -Container "images" `
    -Blob "bikes\racer_green" `
    -Confirm
</code></pre>
<h4 id="delete-an-azure-storage-container">Delete an Azure Storage container</h4>
<h5 id="use-the-azure-portal-8">Use the Azure portal</h5>
<p>In the Azure portal, select <strong>Containers</strong> under <strong>Blob service</strong>, select the container to delete, and then select <strong>Delete</strong> in the toolbar.</p>
<h5 id="use-the-azure-cli-9">Use the Azure CLI</h5>
<pre><code>az storage container delete \
  --account-name contosodata \
  --name "images"
</code></pre>
<h5 id="use-azure-powershell-9">Use Azure PowerShell</h5>
<pre><code>Get-AzStorageAccount `
  -ResourceGroupName "contoso-group" `
  -Name "contosodata" | Remove-AzStorageContainer `
    -Name "images" `
    -Confirm
</code></pre>
<h3 id="manage-azure-file-storage">Manage Azure File storage</h3>
<h4 id="create-a-file-share">Create a file share</h4>
<h5 id="use-the-azure-portal-9">Use the Azure portal</h5>
<p>Select <strong>File shares</strong> in the main pane of the <strong>Overview</strong> page for an Azure Storage account</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-non-relational-data-stores-azure/media/5-file-shares.png" alt="Image of the Overview page for a storage account in the Azure portal. The user has selected the File shares command"><br>
On the <strong>File shares</strong> page, select <strong>+ File share</strong>. Give the file share a name, and optionally specify a quota. Azure allows you to store up to 5 PiB of files across all files shares in a storage account. A quota enables you to limit the amount of space an individual file share consumes, to prevent it from starving other file shares of file storage.</p>
<p>The <strong>Connect</strong> command generates a PowerShell script that you can run to attach to the share from your local computer.</p>
<h5 id="use-azure-storage-explorer">Use Azure Storage Explorer</h5>
<p>Azure Storage Explorer is a utility that enables you to manage Azure Storage accounts from your desktop computer. You can use Storage Explorer to create blob containers and file shares, as well as upload and download files. A version of this utility is also available in the Azure portal, on the <strong>Overview</strong> page for an Azure Storage account.</p>
<p>To create a new file share, right-click <strong>File Shares</strong>, and then select <strong>Create file share</strong>.</p>
<h4 id="upload-and-download-files">Upload and download files</h4>
<p>You can upload and download individual files to and from Azure File storage manually, by using Storage Explorer, the Azure portal, or by connecting the file share to your desktop computer and dragging and dropping files in File Explorer.</p>
<h5 id="azcopy">AzCopy</h5>
<p>However, if you need to transfer a significant number of files in and out of Azure File storage, you should use the AzCopy utility. AzCopy is a command-line utility optimized for transferring large files (and blobs) between your local computer and Azure File storage. It can detect transfer failures, and restart a failed transfer at the point an error occurred - you don’t have to repeat the entire operation.</p>
<h6 id="generate-an-sas-token">Generate an SAS token</h6>
<p>Before you can use AzCopy, you generate a <em>Shared access signature (SAS) token</em>. A SAS token provides controlled, time-limited, anonymous access to services and resources in a storage account; users don’t have to provide any additional credentials. SAS tokens are useful in situations where you don’t know in advance which users will require access to your resources.</p>
<p>You can create an SAS token for connecting to Azure File storage using the Azure portal. On the page for your storage account, under <strong>Settings</strong>, select <strong>Shared access signature</strong>.</p>
<h5 id="upload-files">Upload files</h5>
<pre><code>azcopy copy "myfile.txt" "https://&lt;storage-account-name&gt;.file.core.windows.net/&lt;file-share-name&gt;/myfile.txt&lt;SAS-token&gt;"
</code></pre>
<pre><code>azcopy copy "myfolder" "https://&lt;storage-account-name&gt;.file.core.windows.net/&lt;file-share-name&gt;/myfolder&lt;SAS-token&gt;" --recursive
</code></pre>
<h4 id="download-files">Download files</h4>
<pre><code>azcopy copy "https://&lt;storage-account-name&gt;.file.core.windows.net/myshare/myfolder&lt;SAS-token&gt;" "localfolder" --recursive
</code></pre>
<h1 id="explore-modern-data-warehouse-analytics-in-azure">Explore modern data warehouse analytics in Azure</h1>
<h2 id="examine-components-of-a-modern-data-warehouse">Examine components of a modern data warehouse</h2>
<h3 id="describe-modern-data-warehousing">Describe modern data warehousing</h3>
<p>A data warehouse gathers data from many different sources within an organization. This data is then used as the source for analysis, reporting, and online analytical processing (OLAP).</p>
<p>Data warehouses have to handle <em>big data</em>. Big data is the term used for large quantities of data collected in escalating volumes, at higher velocities, and in a greater variety of formats than ever before. It can be historical (meaning stored) or real time (meaning streamed from the source).</p>
<h4 id="what-is-modern-data-warehousing">What is modern data warehousing?</h4>
<p>A modern data warehouse might contain a mixture of relational and non-relational data, including files, social media streams, and Internet of Things (IoT) sensor data. Azure provides a collection of services you can use to build a data warehouse solution, including Azure Data Factory, Azure Data Lake Storage, Azure Databricks, Azure Synapse Analytics, and Azure Analysis Services. You can use tools such as Power BI to analyze and visualize the data, generating reports, charts, and dashboards.</p>
<h4 id="combine-batch-and-stream-processing">Combine batch and stream processing</h4>
<p>A typical large-scale business requires a combination of up-to-the-second data, and historical information.</p>
<p>Historical data is equally important, to give a business a more stabilized view of trends in performance.</p>
<p>Any modern data warehouse solution must be able to provide access to the streams of <em>raw</em> data, and the <em>cooked</em> business information derived from this data.</p>
<h3 id="explore-azure-data-services-for-modern-data-warehousing">Explore Azure data services for modern data warehousing</h3>
<h4 id="what-is-azure-data-factory">What is Azure Data Factory?</h4>
<p>Azure Data Factory is described as a <em>data integration service</em>. The purpose of Azure Data Factory is to retrieve data from one or more data sources, and convert it into a format that you process. The data sources might present data in different ways, and contain <em>noise</em> that you need to filter out. The <em>interesting</em> data might not be in a suitable format for processing by the other services in your warehouse solution, so you can transform it. You define the work performed by Azure Data Factory as a pipeline of operations.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/examine-components-of-modern-data-warehouse/media/3-data-factory.png" alt="Screenshot of the Azure Data Factory design window, showing an example pipeline"></p>
<h4 id="what-is-azure-data-lake-storage">What is Azure Data Lake Storage?</h4>
<p>A data lake is a repository for large quantities of raw data. Because the data is raw and unprocessed, it’s very fast to load and update, but the data hasn’t been put into a structure suitable for efficient analysis.</p>
<ul>
<li>Data Lake Storage organizes your files into directories and subdirectories for improved file organization. Blob storage can only mimic a directory structure.</li>
<li>Data Lake Storage supports the Portable Operating System Interface (POSIX) file and directory permissions to enable granular Role-Based Access Control (RBAC) on your data.</li>
<li>Azure Data Lake Storage is compatible with the Hadoop Distributed File System (HDFS). Hadoop is highly flexible and programmable analysis service, used by many organizations to examine large quantities of data. All Apache Hadoop environments can access data in Azure Data Lake Storage Gen2.</li>
</ul>
<p>In an Azure Data Services data warehouse solution, data is typically loaded into Azure Data Lake Storage before being processed into a structure that enables efficient analysis in Azure Synapse Analytics. You can use a service such as Azure Data Factory (described above) to ingest and load the data from a variety of sources into Azure Data Lake Storage.</p>
<h4 id="what-is-azure-databricks">What is Azure Databricks?</h4>
<p>Azure Databricks is an Apache Spark environment running on Azure to provide big data processing, streaming, and machine learning. Apache Spark is a highly efficient data processing engine that can consume and process large amounts of data very quickly. There are a significant number of Spark libraries you can use to perform tasks such as SQL processing, aggregations, and to build and train machine learning models using your data.</p>
<p>You can create Databricks scripts and query data using languages such as R, Python, and Scala. You write your Spark code using <em>notebooks</em>. A notebook contains <em>cells</em>, each of which contains a separate block of code. When you run a notebook, the code in each cell is passed to Spark in turn for execution. The image below shows a cell in a workbook that runs a query and generates a graph.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/examine-components-of-modern-data-warehouse/media/3-databricks.png" alt="Graphic showing a notebook running in Azure Databricks"><br>
Azure Databricks also supports structured stream processing.</p>
<h4 id="what-is-azure-synapse-analytics">What is Azure Synapse Analytics?</h4>
<p>Azure Synapse Analytics is an analytics engine. It’s designed to process large amounts of data very quickly.</p>
<p>Using Synapse Analytics, you can ingest data from external sources, such as flat files, Azure Data Lake, or other database management systems, and then transform and aggregate this data into a format suitable for analytics processing. You can perform complex queries over this data and generate reports, graphs, and charts.</p>
<p>Azure Synapse Analytics leverages a massively parallel processing (MPP) architecture. This architecture includes a control node and a pool of compute nodes.</p>
<p>The <em>Control</em> node is the brain of the architecture. It’s the front end that interacts with all applications. When you submit a processing request, the Control node transforms it into smaller requests that run against distinct subsets of the data in parallel.</p>
<p>The <em>Compute</em> nodes provide the computational power. The data to be processed is distributed evenly across the nodes.</p>
<p>Azure Synapse Analytics supports two computational models: SQL pools and Spark pools.</p>
<p>In a SQL pool, each compute node uses an Azure SQL Database and Azure Storage to handle a portion of the data.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/examine-components-of-modern-data-warehouse/media/3-synapse.png" alt="Graphic showing the structure of Azure Synapse Analytics"><br>
You submit queries in the form of Transact-SQL statements, and Azure Synapse Analytics runs them. However, unlike an ordinary SQL Server database engine, Azure Synapse Analytics can receive data from a wide variety of sources. To do this, Azure Synapse Analytics uses a technology named PolyBase. PolyBase enables you to retrieve data from relational and non-relational sources, such as delimited text files, Azure Blob Storage, and Azure Data Lake Storage. You can save the data read in as SQL tables within the Synapse Analytics service.</p>
<p>You can only scale a SQL pool when it’s not running a Transact-SQL query.</p>
<p>In a Spark pool, the nodes are replaced with a Spark cluster. You run Spark jobs comprising code written in Notebooks, in the same way as Azure Databricks. You can write the code for notebook in C#, Python, Scala, or Spark SQL (a different dialect of SQL from Transact-SQL). As with a SQL pool, the Spark cluster splits the work out into a series of parallel tasks that can be performed concurrently. You can save data generated by your notebooks in Azure Storage or Data Lake Storage.</p>
<p>Spark is optimized for in-memory processing. A Spark job can load and cache data into memory and query it repeatedly. In-memory computing is much faster than disk-based applications, but requires additional memory resources.</p>
<p>Spark pools can have autoscaling enabled, so that pools scale by adding or removing nodes as needed. Autoscaling can occur while processing is active.</p>
<p>Azure Synapse Analytics can consume a lot of resources. If you aren’t planning on performing any processing for a while, you can pause the service.</p>
<h4 id="what-is-azure-analysis-services">What is Azure Analysis Services?</h4>
<p>Azure Analysis Services enables you to build tabular models to support online analytical processing (OLAP) queries. You can combine data from multiple sources, including Azure SQL Database, Azure Synapse Analytics, Azure Data Lake store, Azure Cosmos DB, and many others. You use these data sources to build models that incorporate your business knowledge. A model is essentially a set of queries and expressions that retrieve data from the various data sources and generate results. The results can be cached in-memory for later use, or they can be calculated dynamically, directly from the underlying data sources.</p>
<h5 id="compare-analysis-services-with-synapse-analytics">Compare Analysis Services with Synapse Analytics</h5>
<p>Azure Analysis Services has significant functional overlap with Azure Synapse Analytics, but it’s more suited for processing on a smaller scale.</p>
<p>Use Azure Synapse Analytics for:</p>
<ul>
<li>Very high volumes of data (multi-terabyte to petabyte sized datasets).</li>
<li>Very complex queries and aggregations.</li>
<li>Data mining, and data exploration.</li>
<li>Complex ETL operations.</li>
<li>Low to mid concurrency (128 users or fewer).</li>
</ul>
<p>Use Azure Analysis Services for:</p>
<ul>
<li>Smaller volumes of data (a few terabytes).</li>
<li>Multiple sources that can be correlated.</li>
<li>High read concurrency (thousands of users).</li>
<li>Detailed analysis, and drilling into data, using functions in Power BI.</li>
<li>Rapid dashboard development from tabular data.</li>
</ul>
<h5 id="combine-analysis-services-with-synapse-analytics">Combine Analysis Services with Synapse Analytics</h5>
<p>Many scenarios can benefit from using Synapse Analytics and Analysis Services together. If you have large amounts of ingested data that require preprocessing, you can use Synapse Analytics to read this data and manipulate it into a model that contains business information rather than a large amount of raw data. You can then use Analysis Services to perform detailed interrogation of this information, and visualize the results of these inquiries with Power BI.</p>
<h4 id="what-is-azure-hdinsight">What is Azure HDInsight?</h4>
<p>Azure HDInsight is a big data processing service, that provides the platform for technologies such as Spark in an Azure environment. HDInsight implements a clustered model that distributes processing across a set of computers. This model is similar to that used by Synapse Analytics, except that the nodes are running the Spark processing engine rather than Azure SQL Database. As well as Spark, HDInsight supports streaming technologies such as Apache Kafka, and the Apache Hadoop processing model.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/examine-components-of-modern-data-warehouse/media/3-hdinsight.png" alt="Graphic showing how HDInisght fits into a data warehousing solution"><br>
<em>Hive</em> is a SQL-like query facility that you can use with an HDInsight cluster to examine data held in a variety of formats. You can use it to create, load, and query external tables, in a manner similar to PolyBase for Azure Synapse Analytics.</p>
<h2 id="explore-data-ingestion-in-azure">Explore data ingestion in Azure</h2>
<h3 id="describe-common-practices-for-data-loading">Describe common practices for data loading</h3>
<p>In a big data system, data ingestion has to be fast enough to capture the large quantities of data that may be heading your way, and have enough compute power to process this data in a timely manner.</p>
<h4 id="ingest-data-using-azure-data-factory">Ingest data using Azure Data Factory</h4>
<p>Data Factory provides an <em>orchestration</em> engine. Orchestration is the process of directing and controlling other services, and connecting them together, to allow data to flow between them. Data Factory uses orchestration to combine and automate sequences of tasks that use different services to perform complex operations.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-ingestion-azure/media/2-enterprise-bi-adf.png" alt="Image summarizing the role of Azure Data Factory for ingesting and processing data"></p>
<h5 id="understand-linked-services">Understand linked services</h5>
<p>Data Factory moves data from a data source to a destination. A linked service provides the information needed for Data Factory to connect to a source or destination. The information a linked service contains varies according to the resource.</p>
<h5 id="understand-datasets">Understand datasets</h5>
<p>A dataset in Azure Data Factory represents the data that you want to ingest (input) or store (output).</p>
<h5 id="understand-pipelines">Understand pipelines</h5>
<p>A pipeline is a logical grouping of activities that together perform a task. The activities in a pipeline define actions to perform on your data.</p>
<p>Pipelines don’t have to be linear. You can include logic activities that repeatedly perform a series of tasks while some condition is true using a <em>ForEach</em> activity, or follow different processing paths depending on the outcome of previous processing using an <em>If Condition</em> activity.</p>
<p>Sometimes when ingesting data, the data you’re bringing in can have different column names and data types to those required by the output. In these cases, you can use a mapping to transform your data from the input format to the output format. The screenshot below shows the mapping canvas for the <em>Copy Data</em> activity.</p>
<p>You can run a pipeline manually, or you can arrange for it to be run later using a trigger.</p>
<h4 id="ingest-data-using-polybase">Ingest data using PolyBase</h4>
<p>PolyBase is a feature of SQL Server and Azure Synapse Analytics that enables you to run Transact-SQL queries that read data from external data sources. PolyBase makes these external data sources appear like tables in a SQL database. Using PolyBase, you can read data managed by Hadoop, Spark, and Azure Blob Storage, as well as other database management systems such as Cosmos DB, Oracle, Teradata, and MongoDB.</p>
<p>Azure SQL Database does not support PolyBase. Azure Data Factory provides PolyBase support for loading data.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-ingestion-azure/media/2-polybase.png" alt="Image showing SQL Database using PolyBase to access external data"></p>
<h4 id="ingest-data-using-sql-server-integration-services">Ingest data using SQL Server Integration Services</h4>
<p>SQL Server Integration Services (SSIS) is a platform for building enterprise-level data integration and data transformations solutions.</p>
<p>SSIS can extract and transform data from a wide variety of sources such as XML data files, flat files, and relational data sources, and then load the data into one or more destinations.</p>
<p>You can use the graphical SSIS tools to create solutions without writing a single line of code. You can also program the extensive Integration Services object model to create packages programmatically and code custom tasks and other package objects.</p>
<p>SSIS is an on-premises utility. However, Azure Data factory allows you to run your existing SSIS packages as part of a pipeline in the cloud. This allows you to get started quickly without having to rewrite your existing transformation logic.</p>
<h4 id="ingest-data-using-azure-databricks">Ingest data using Azure Databricks</h4>
<p>Azure Databricks is an analytics platform optimized for the Microsoft Azure cloud services platform. Databricks is based on Spark, and is integrated with Azure to streamline workflows. You write and run Spark code using <em>notebooks</em>. The scalability of Azure Databricks makes it an ideal platform for performing complex data ingestion and analytics tasks.</p>
<h2 id="explore-data-storage-and-processing-in-azure">Explore data storage and processing in Azure</h2>
<h3 id="describe-data-storage-and-processing-with-azure">Describe data storage and processing with Azure</h3>
<h4 id="what-is-azure-synapse-analytics-1">What is Azure Synapse Analytics?</h4>
<p>Azure Synapse Analytics is a generalized analytics service. You can use it to read data from many sources, process this data, generate various analyses and models, and save the results.</p>
<p>You can select between two technologies to process data:</p>
<ul>
<li><em>Transact-SQL</em>. This is the same dialect of SQL used by Azure SQL Database, with some extensions for reading data from external sources, such as databases, files, and Azure Data Lake storage.</li>
<li><em>Spark</em>. This is the same open-source technology used to power Azure Databricks. You write your analytical code using notebooks in a programming language such as C#, Scala, Python, or SQL.</li>
</ul>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-storage-processing-azure/media/2-synapse.png" alt="Image showing the elements of Azure Synapse Analytics"></p>
<h4 id="what-is-azure-databricks-1">What is Azure Databricks?</h4>
<p>Azure Databricks is an analytics platform optimized for the Microsoft Azure cloud services platform. Designed with the founders of Apache Spark, Databricks is integrated with Azure to provide one-click setup, streamlined workflows, and an interactive workspace that enables collaboration between data scientists, data engineers, and business analysts.</p>
<p>Databricks can process data held in many different types of storage, including Azure Blob storage, Azure Data Lake Store, Hadoop storage, flat files, databases, and data warehouses. Databricks can also process streaming data. Databricks uses an extensible architecture based on drivers.</p>
<p>A <em>driver</em> is a piece of code that connects to a specific data source and enables you to read and write that source.</p>
<h5 id="what-is-azure-hdinsight-1">What is Azure HDInsight?</h5>
<p>Azure HDInsight is a managed analytics service in the cloud. It’s based on Apache Hadoop, a collection of open-source tools and utilities that enable you to run processing tasks over large amounts of data. HDInsight uses a clustered model, similar to that of Synapse Analytics. HDInsight stores data using Azure Data Lake storage. You can use HDInsight to analyze data using frameworks such as Hadoop Map/Reduce, Apache Spark, Apache Hive, Apache Kafka, Apache Storm, R, and more.</p>
<p>Hadoop Map/Reduce uses a simple framework to split a task over a large dataset into a series of smaller tasks over subsets of the data that can be run in parallel, and the results then combined. You write your Map/Reduce code in a language such as Java, and then submit this code as a job to the Hadoop cluster. Hadoop Map/Reduce has largely been replaced by Spark, which offers a more advanced set of operations and a simpler interface.</p>
<p>Apache Hive provides interactive SQL-like facilities for querying, aggregating, and summarizing data.</p>
<p>Apache Kafka is a clustered streaming service that can ingest data in real time.</p>
<p>Apache Storm is a scalable, fault tolerant platform for running real-time data processing applications. Storm can process high volumes of streaming data using comparatively modest computational requirements. Storm can interoperate with a variety of event sources, including Azure Event Hubs, Azure IoT Hub, Apache Kafka, and RabbitMQ (a message queuing service). Storm can also write to data stores such as HDFS, Hive, HBase, Redis, and SQL databases.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-storage-processing-azure/media/2-hdinsight.png" alt="Image showing the elements of HDInsight"></p>
<h4 id="what-is-azure-data-factory-1">What is Azure Data Factory?</h4>
<p>Azure Data Factory is a service that can ingest large amounts of raw, unorganized data from relational and non-relational systems, and convert this data into meaningful information. Data Factory provides a scalable and programmable ingestion engine that you can use to implement complex hybrid extract-transform-load (ETL), extract-load-transform (ELT), and data integration projects.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-storage-processing-azure/media/2-data-factory-pipeline.png" alt="Image showing a Data Factory pipeline"></p>
<h4 id="what-is-azure-data-lake">What is Azure Data Lake?</h4>
<p>Azure Data Lake is a collection of analytics and storage services that you can combine to implement a big data solution. It comprises three main elements:</p>
<ul>
<li>Data Lake Store</li>
<li>Data Lake Analytics</li>
<li>HDInsight</li>
</ul>
<h5 id="what-is-data-lake-store">What is Data Lake Store?</h5>
<p>Data Lake Store provides a file system that can store near limitless quantities of data. It uses a hierarchical organization (like the Windows and Linux file systems), but you can hold massive amounts of raw data (blobs) and structured data.</p>
<p>Azure Data Lake Store is compatible with the Hadoop Distributed File System (HDFS).</p>
<p>Azure Data Lake Store provides granular security over data, using Access Control Lists. If you are more familiar with Linux, you can use POSIX-style permissions to grant read, write, and search access based on file ownership and group membership of users.</p>
<h5 id="what-is-data-lake-analytics">What is Data Lake Analytics?</h5>
<p>Azure Data Lake Analytics is an on-demand analytics job service that you can use to process big data. It provides a framework and set of tools that you use to analyze data held in Microsoft Azure Data Lake Store, and other repositories. You write jobs that contain queries to transform data and extract insights.</p>
<p>You define a job using a language called U-SQL. This is a hybrid language that takes features from both SQL and C#, and provides declarative and procedural capabilities that you can use to process data.</p>
<pre><code>@priceData =
    EXTRACT Ticker string,
            Price int
    FROM "/StockMarket/StockPrices.csv"
    USING Extractors.Csv(skipFirstNRows: 1);

@maxPrices =
    SELECT Ticker, MAX(Price) AS MaxPrice
    FROM @priceData
    GROUP BY Ticker;

OUTPUT @maxPrices   
    TO "/output/MaxPrices.csv"
    USING Outputters.Csv(outputHeader: true);
</code></pre>
<p>It’s important to understand that the U-SQL code only provides a description of the work to be performed. Azure Data Lake Analytics determines how best to actually carry out this work.</p>
<h3 id="explore-azure-synapse-analytics">Explore Azure Synapse Analytics</h3>
<h4 id="what-are-the-components-of-azure-synapse-analytics">What are the components of Azure Synapse Analytics?</h4>
<p>Azure Synapse Analytics is an integrated analytics service that allows organizations to gain insights quickly from all their data at any hyperscale, from both data warehouses and big data analytics systems.</p>
<p>Azure Synapse is composed of the following elements:</p>
<ul>
<li><strong>Synapse SQL pool</strong>: This is a collection of servers running Transact-SQL. Transact-SQL is the dialect of SQL used by Azure SQL Database, and Microsoft SQL Server. You write your data processing logic using Transact-SQL.</li>
<li><strong>Synapse Spark pool</strong>: This is a cluster of servers running Apache Spark to process data. You write your data processing logic using one of the four supported languages: Python, Scala, SQL, and C# (via .NET for Apache Spark). Spark pools support Azure Machine Learning through integration with the SparkML and AzureML packages.</li>
<li><strong>Synapse Pipelines</strong>: A Synapse pipeline is a logical grouping of activities that together perform a task. The activities in a pipeline define actions to perform on your data.</li>
<li><strong>Synapse Link</strong>: This component allows you to connect to Cosmos DB. You can use it to perform near real-time analytics over the operational data stored in a Cosmos DB database.</li>
<li><strong>Synapse Studio</strong>: This is a web user interface that enables data engineers to access all the Synapse Analytics tools.</li>
</ul>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-storage-processing-azure/media/3-azure-synapse-analytics-overview.png" alt="Diagram showing the components of Azure Synapse Analytics. Synapse Studio, Synapse Pipelines, Synapse SQL pools, Synapse Spark pools, and Synapse Link"></p>
<h4 id="what-are-sql-pools">What are SQL pools?</h4>
<p>When you use Synapse SQL, your analytics workload runs using a SQL pool. In a SQL pool, the Control and Compute nodes in the cluster run a version of Azure SQL Database that supports distributed queries. You define your logic using Transact-SQL statements. You send your Transact-SQL statements to the control node, which splits up the work into queries that operate over a subset of the data, and then sends these smaller queries to the compute nodes. The data is split into chunks called <em>distributions</em>. A distribution is the basic unit of storage and processing for parallel queries that run on distributed data.</p>
<p>The control and compute nodes use the Data Movement Service (DMS) to move data across the nodes as necessary to run queries in parallel and return accurate results.</p>
<p>Synapse Analytics uses a technology called <em>PolyBase</em> to make external data look like SQL tables. You can run queries against these tables directly, or you can transfer the data into a series of SQL tables managed by Synapse Analytics for querying later. Synapse uses Azure Storage to manage your data while it’s being processed.</p>
<p>By default, an on-demand SQL pool is created in each Azure Synapse Analytics workspace. You can then provision additional pools, either on-demand or provisioned.</p>
<p>On-demand pools only allow you to query data held in external files. If you want to ingest and load the data into Synapse Analytics, you must create your own SQL pool.</p>
<p>Azure Synapse Analytics is designed to run queries over massive datasets. You can manually scale the SQL pool up to 60 nodes. You can also <em>pause</em> a SQL pool if you don’t require it for a while.</p>
<p>Use SQL pools in Synapse Analytics for the following scenarios:</p>
<ul>
<li>
<p><em>Complex reporting</em>. You can use the full power of Transact-SQL to run complex SQL statements that summarize and aggregate data.</p>
</li>
<li>
<p><em>Data ingestion</em>. PolyBase enables you to retrieve data from many external sources and convert it into a tabular format. You can reformat this data and save it as tables and materialized views in Azure Synapse.</p>
</li>
</ul>
<h4 id="what-are-spark-pools">What are Spark pools?</h4>
<p>Synapse Spark runs clusters based on Apache Spark rather than Azure SQL Database. You write your analytics jobs as notebooks, using code written in Python, Scala, C#, or Spark SQL (this is a different dialect from Transact-SQL).</p>
<p>Spark pools and SQL pools can coexist in the same Azure Synapse Analytics instance.</p>
<p>Notebooks also allow you to visualize data through graphs, and transform data as it’s loaded. The data can then be used by Spark Machine Learning (SparkML) and Azure Machine Learning (AzureML) to train machine learning models that support artificial intelligence.</p>
<p>Spark pools provide the basic building blocks for performing in-memory cluster computing. A Spark job can load and cache data into memory and query it repeatedly. In-memory computing is much faster than disk-based applications.</p>
<p>Spark pools can have autoscaling enabled, so that pools scale by adding or removing nodes as needed. Also, Spark pools can be shut down with no loss of data since all the data is stored in Azure Storage or Data Lake Storage.</p>
<p>Spark pools in Synapse Analytics are especially suitable for the following scenarios:</p>
<ul>
<li>
<p><em>Data Engineering/Data Preparation</em>. Apache Spark includes many language features to support preparation and processing of large volumes of data so that it can be made more valuable and then consumed by other services within Synapse Analytics.</p>
</li>
<li>
<p><em>Machine Learning</em>. Apache Spark comes with MLlib, a machine learning library built on top of Spark that you can use from a Spark pool in Synapse Analytics. Spark pools in Synapse Analytics also include Anaconda, a Python distribution with a variety of packages for data science including machine learning.</p>
</li>
</ul>
<h4 id="what-are-synapse-pipelines">What are Synapse pipelines?</h4>
<p>A pipeline is a logical grouping of activities that together perform a task. The activities in a pipeline define actions to perform on your data. Synapse pipelines use the same Data Integration engine used by Azure Data Factory.</p>
<p>You can create codeless data flows that let you do complex mappings and transformations on data as it flows into your analytic solutions. The example below shows a pipeline with three activities. The pipeline ingests data, and then uses a Spark notebook to generate a machine learning model. The Azure function at the end of the pipeline tests the machine learning model to validate it.</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-storage-processing-azure/media/3-pipeline.png" alt="Screenshot of a simple pipeline containing three activities"></p>
<h5 id="what-is-synapse-link">What is Synapse Link?</h5>
<p>Azure Synapse Link for Azure Cosmos DB is a cloud-native hybrid transactional and analytical processing (HTAP) capability that enables you to run near real-time analytics over operational data stored in Azure Cosmos DB.</p>
<p>Synapse link uses a feature of Cosmos DB named <em>Cosmos DB Analytical Store</em>. Cosmos DB Analytical Store contains a copy of the data in a Cosmos DB container, but organized as a column store. Column stores are a more optimal format for running analytical workloads that need to aggregate data down a column rather than across a row, such as generating sum totals, averages, maximum or minimum values for a column.</p>
<p>Azure Synapse Link enables you to run workloads that retrieve data directly from Cosmos DB and run analytics workloads using Azure Synapse Analytics. The data doesn’t have to go through an ETL (extract, transform, and load) process because the data isn’t copied into Synapse Analytics; it remains in the Cosmos DB analytical store.</p>
<p>Synapse link has a wide range of uses, including:</p>
<ul>
<li>
<p><em>Supply chain analytics and forecasting</em>.</p>
</li>
<li>
<p><em>Operational reporting</em>.</p>
</li>
<li>
<p><em>Batch data integration and orchestration</em>.</p>
</li>
<li>
<p><em>Real-time personalization</em>.</p>
</li>
<li>
<p><em>IoT maintenance</em>.</p>
</li>
</ul>
<h4 id="what-is-synapse-studio">What is Synapse Studio?</h4>
<p>Synapse Studio is a web interface that enables you to create pools and pipelines interactively. With Synapse Studio you can develop, test, and debug Spark notebooks and Transact-SQL jobs</p>
<p><img src="https://docs.microsoft.com/en-us/learn/wwl-data-ai/explore-data-storage-processing-azure/media/3-synapse-studio.png" alt="Screenshot Synapse Studio"></p>
<h2 id="get-started-building-with-power-bi">Get started building with Power BI</h2>
<h3 id="introduction">Introduction</h3>
<p><strong>Microsoft Power BI</strong> is a collection of software services, apps, and connectors that work together to turn your unrelated sources of data into coherent, visually immersive, and interactive insights.</p>
<p><strong>Power BI</strong> can be simple and fast, capable of creating quick insights from an Excel workbook or a local database. But <strong>Power BI</strong> is also robust and enterprise-grade, ready not only for extensive modeling and real-time analytics, but also for custom development.</p>
<h4 id="the-parts-of-power-bi">The parts of Power BI</h4>
<p>Power BI consists of a Microsoft Windows desktop application called <strong>Power BI Desktop</strong>, an online SaaS (<em>Software as a Service</em>) service called the <strong>Power BI service</strong>, and mobile Power BI <strong>apps</strong> that are available on any device, with native mobile BI apps for Windows, iOS, and Android.</p>
<h4 id="how-power-bi-matches-your-role">How Power BI matches your role</h4>
<p>How you use Power BI might depend on your role on a project or a team.</p>
<h3 id="use-power-bi">Use Power BI</h3>
<p>The activities and analyses that you’ll learn with Power BI generally follow a common flow. The <strong>common flow</strong> of activity looks like this:</p>
<ol>
<li>Bring data into Power BI Desktop and create a report.</li>
<li>Publish to the Power BI service, where you can create new visualizations or build dashboards.</li>
<li>Share dashboards with others, especially people who are on the go.</li>
<li>View and interact with shared dashboards and reports in Power BI Mobile apps.</li>
</ol>
<h3 id="building-blocks-of-power-bi">Building blocks of Power BI</h3>
<p>Everything you do in Microsoft Power BI can be broken down into a few basic <strong>building blocks</strong>. After you understand these building blocks, you can expand on each of them and begin creating elaborate and complex reports.</p>
<p>Here are the basic building blocks in Power BI:</p>
<ul>
<li>Visualizations</li>
<li>Datasets</li>
<li>Reports</li>
<li>Dashboards</li>
<li>Tiles</li>
</ul>
<h4 id="visualizations">Visualizations</h4>
<p>A <strong>visualization</strong> (sometimes also referred to as a <strong>visual</strong>) is a visual representation of data, like a chart, a color-coded map, or other interesting things you can create to represent your data visually</p>
<h4 id="datasets">Datasets</h4>
<p>A <strong>dataset</strong> is a collection of data that Power BI uses to create its visualizations. <strong>Datasets</strong> can also be a combination of many different sources, which you can filter and combine to provide a unique collection of data (a dataset) for use in Power BI.</p>
<p>An important and enabling part of Power BI is the multitude of data <strong>connectors</strong> that are included. Whether the data you want is in Excel or a Microsoft SQL Server database, in Azure or Oracle, or in a service like Facebook, Salesforce, or MailChimp, Power BI has built-in data connectors that let you easily connect to that data, filter it if necessary, and bring it into your dataset.</p>
<h4 id="reports">Reports</h4>
<p>In Power BI, a <strong>report</strong> is a collection of visualizations that appear together on one or more pages. Just like any other report you might create for a sales presentation or write for a school assignment, a report in Power BI is a collection of items that are related to each other.</p>
<h4 id="dashboards">Dashboards</h4>
<p>When you’re ready to share a report, or a collection of visualizations, you create a <strong>dashboard</strong>. Much like the dashboard in a car, a Power BI <strong>dashboard</strong> is a collection of visuals from a single page that you can share with others. Often, it’s a selected group of visuals that provide quick insight into the data or story you’re trying to present. A dashboard must fit on a single page, often called a canvas.</p>
<h4 id="tiles">Tiles</h4>
<p>In Power BI, a <strong>tile</strong> is a single visualization on a dashboard. It’s the rectangular box that holds an individual visual.</p>
<h3 id="tour-and-use-the-power-bi-service">Tour and use the Power BI service</h3>
<p>An <strong>app</strong> is a collection of preset, ready-made visuals and reports that are shared with an entire organization.</p>
<h4 id="create-out-of-the-box-dashboards-with-cloud-services">Create out-of-the-box dashboards with cloud services</h4>
<p>With Power BI, connecting to data is easy. From the Power BI service, you can just select the <strong>Get Data</strong> button in the lower-left corner of the home page.</p>
<p>The <em>canvas</em> (the area in the center of the Power BI service) shows you the available sources of data in the Power BI service.</p>
<p>For these software services, the <strong>Power BI service</strong> provides a collection of ready-made visuals that are pre-arranged on dashboards and reports for your organization. This collection of visuals is called an <strong>app</strong>.</p>
<h4 id="update-data-in-the-power-bi-service">Update data in the Power BI service</h4>
<p>You can also choose to <strong>update</strong> the dataset for an app, or other data that you use in Power BI. To set update settings, select the schedule update icon for the dataset that you want to update, and then use the menu that appears.</p>
<p>The <strong>Datasets</strong> tab is selected on the <strong>Settings</strong> page that appears. In the right pane, select the arrow next to <strong>Scheduled refresh</strong> to expand that section.</p>

