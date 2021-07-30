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

