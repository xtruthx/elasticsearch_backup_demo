## Recommendation for naming a snapshot during automation

It is highly recommended to use a date in your snapshot-name so you can easily automate the snapshot and retention calculating stuff. 
Curator the elastic tool for maintaining Elasticsearch Indices is providing a date math filter for date-time strings in index names.

`
curl -X PUT "localhost:9200/_snapshot/nfs_repository/%3Cbackup-%7Bnow%2Fd%7D%3E"
`

You need to use the date math function like explained here: [date math](https://www.elastic.co/guide/en/elasticsearch/reference/current/date-math-index-names.html)

