## On option to automated snapshot name

This can be reached with date math function and unicode encoding

`
curl -X PUT "localhost:9200/_snapshot/nfs_repository/%3Cbackup-%7Bnow%2Fd%7D%3E"
`

