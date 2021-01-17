# DataStax Holiday Hackathon
 
## Team Hack-The-Planet

## GitHub Archive Integrations With Astra

## Project Description  

We wanted to answer some questions like: 

*	What projects are our co-workers working on in Github?
*	Who contributes to repo apache/cassandra?
*	Who contributes to repo stargate/stargate?

To answer these questions we wanted to build a GitHub Archive integration with Astra.  In continuing our theme for using new integration tools not already known as being useful for astra; we chose Nifi and eCharts from apache.org.   To reduce bulk of data involved we leveraged GCP’s BigQuery against the public dataset provided by Github Archive to filter based on repos and @datastax.com matches.   

During this Hackathon our team worked independently on the following areas:  Infrastructure & Automation, Data Modeling & Aggregation, and Visualization.   

At the infrastructure level we provided a fully automated raw data ingestion platform based on Apache NiFi. The data pipeline is pulling data from GCS bucket in csv or json formats and executing the appropriate Stargate endpoints to insert JSON (document api - no schema) or CSV (rest api - schema).   

On the Data Modeling & Aggregation side we ingested and viewed raw data using BigQuery, both ODBC & JDBC Drivers, and Astra Studio.  These tools helped us inspect raw data to formulate final normalized tables and create schemas needed to support automated data pipeline aggregations for csv based cql tables.  

On the Visualization side we leveraged an incubating project at apache.org called eCharts which is accepting of the JSON output of our normalized data sources.    Additionally, BI Tool Teams created similar visualizations to prove equal BI Tool capability.

This was a no-code approach allowing silo’d team members to pass data between disconnected systems and create ad-hoc visualizations knowing the teams had an inherit capability to create appropriate data sources on the fly.  

Some of our ideas to build on this project for the future are to use the integration lessons learned to create an internal application allowing us to fully leverage this data source and other public and private GitHub data sources to enable additional business ideas based on GitHub interactions.


Built With:  [Astra](https://astra.datastax.com/), [Stargate](https://stargate.io/), [GitHub Archive](https://www.gharchive.org/), GCP: [BigQuery](https://cloud.google.com/bigquery) & [GCS](https://cloud.google.com/storage), [NiFi](http://nifi.apache.org/), [eCharts](http://echarts.apache.org/)
