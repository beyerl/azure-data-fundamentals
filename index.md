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

