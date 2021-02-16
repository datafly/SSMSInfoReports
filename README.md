# SSMSInfoReports
<h3>SQL Server Management Studio (SSMS) Information Custom Reports (V7)</h3>

This set of custom reports is intended to provide a quick overview of an instance and its databases. It is easier to answer the main questions that arise when you discover and diagnose a new server or database.

Reports that come with SSMS installation are useful but they do not provide this kind of summary information. They also lack some advanced information that is accessible only through queries. One of the benefits of using reports rather than queries is their ability to be exported or printed.

<p><img src="http://blog.datafly.pro/public/images/SSMSInfoReports/SSMSInfoReportSample.jpg" alt="Index report" width="605" height="381" /></p>

You'll get various information, easy readable :
<ul>
<li>Server information : version, edition, build, os platform, hardware, services, configuration options, memory configuration, security, etc… </li>
<li>Storage : disk allocated, file sizes and allocation for all databases </li>
<li>Last errors in SQL Server errorlog </li>
<li>SQL Agent jobs information and history </li>
<li>Always On Availability Groups information </li>
<li>Performance information : wait states, cpu, memory usage and main performance counters, io latency, tempdb utilization, etc… </li>
<li>Databases informations : database options, storage allocation, transaction logs and backups information, mixed collations, objects information, etc... </li>
<li>Tables and index informations : primary keys (clustered, nonclustered, no primary key), unique constraints, existing indexes, tables without index, size of index keys, etc… </li> </ul>

TSQL scripts of these reports are coming from various sources : my own scripts and some other inspired by well known SQL Server experts.

<h2>Installation and usage</h2>
Copy the rdl files to a folder that is accessible to the SQL Server Management Studio client. Right-click on the SQL instance in object explorer, select "custom reports" and browse to the location of the rdl file. The main report is "Main Server Dashboard".

The reports are intended to be used with SSMS 2012 and later (they don't work with earlier SSMS versions) but they can get information from instances from 2008 to 2019.

Sysadmin rights are required to run the reports: dmv, ole automation and extended stored procedures are used to access all information.

These reports are provided "as is". Even the risk is low, use with your production servers is at your own risk.

<h2>Reports description</h2>
<ul>
<li>Main Server Dashboard.rdl : main information and starting point, other reports are linked to this one  (but they can be used also separately). 
<li>Server Report.rdl : instance information </li>
<li>Always On Report : availability groups information, new in V7 </li>
<li>All Databases Report.rdl : databases overview </li>
<li>Server Performance.rdl : instance performance informations </li>
<li>Database Report.rdl : general database information. Could also to be run from a database in object explorer. </li>
<li>Tables Report : tables informations. Could also to be run from a database in object explorer. </li>
<li>Index Report : index informations. Could also to be run from a database or a single table object in object explorer. </li>
<li>Statistics Report : informations about columns and index statistics. Could also to be run from a database, a single table or a single statistic. </li>
<li>Missing Index Report : show missing index, for one or for all databases </li>
<li>Jobs report : a dashboard for monitoring jobs execution and performance </li>
<li>Jobs history planning report : shows history of last 24 hours, new in V7 </li>
<li>Job detailed report : detailed information, could also be run from a single job in SSMS </li>
</ul>
Reports are linked to each other and the top report is "Main Server Dashboard.rdl" : 
<p><img src="http://blog.datafly.pro/public/images/SSMSInfoReports/SSMSInfoReports_Diagram7.jpg" alt="Reports diagram" width="589" height="304" /></p>
You can also use some reports in the context : database report with right click on a database, index report with right click on a table, ...
<h2>Release history</h2>
<ul>
  <li>7.0   : new reports added (AlwaysOn, Jobs planning history), improvements for all reports </li>
  <li>6.5.2 : precedent release </li>
</ul>

