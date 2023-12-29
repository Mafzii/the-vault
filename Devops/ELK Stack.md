### Elasticsearch
- Search engine for different applications
	- complex search functions for sifting data
	- for querying structured data in a DB-like format
- For my use case: searching through logs and extracting important information
	- application performance management (APM)

- Elasticsearch stores data as documents using [[REST API's]] through the UI
	- A document is like a row in a DB table
	- Documents have fields and are JSON objects
- A single large index (data source) is divided into multiple smaller shards allowing for parallel processing

- 