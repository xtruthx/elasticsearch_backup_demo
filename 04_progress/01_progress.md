## Show status of a repository


`
curl -X GET "localhost:9200/_snapshot/nfs_repository/_current"
`

# Show status of a snapshot

To show the status of running snapshot you need use the full name of it.

`
curl -X GET "localhost:9200/_snapshot/nfs_repositroy/snapshot_1/_status"
`

## Stopping and delete Snapshot

If you want to delete a snapshot you use "DELETE" with the correct running snapshot name the same is used if you want to
stop a running snapshot.

`
curl -X DELETE "localhost:9200/_snapshot/nfs_repository/snapshot_1"
`
