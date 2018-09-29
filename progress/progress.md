## show status of a repository

`
curl -X GET "localhost:9200/_snapshot/nfs_repository/_current"
`

## Stop a snapshot

curl -X GET "localhost:9200/_snapshot/nfs_repositroy/snapshot_1/_status"


## show status of snaphshot

`
curl -X DELETE "localhost:9200/_snapshot/nfs_repository/snapshot_1"
`
