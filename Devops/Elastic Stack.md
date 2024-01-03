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

### Logstash
- input -> filter -> output pipelines
- The data from the input is read event by event
- An event can be declared by the creator of the pipeline to start and end based on certain conditions (e.g. regex)
- Any data source can be used as input
- Starting logstash by reading a file will, by default, tail the file and wait for changes
- Use grok filters to extract information using regex