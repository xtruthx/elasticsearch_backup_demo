## Take a snapshot of all indices

You can trigger a snapshot with "curl XPUT" Method

`
curl -X PUT "localhost:9200/_snapshot/nfs_repository/snapshot_1?wait_for_completion=true"
`
This triggers a snapshot with the given name snapshot_1. At this point a valid name must be give to create a snapshot, no name can be used twice.
That means if you do some scripting to automate the snapshot you should take care about that fact.


## Advanced Snapshot settings from specific indices

During taking a snapshot you can also use some helpful options followed are some important one mentioned. It is necessary to declare them as json body.


`
curl -X PUT "localhost:9200/nfs_snapshot/my_backup/snapshot_2?wait_for_completion=true" -H 'Content-Type: application/json' -d'
{
  "indices": "index_1,index_2",
  "ignore_unavailable": true,
  "include_global_state": false,
  "partial": true
}
'
`

### Explained Settings

* ignore_unavailable: This will prevent the snapshot from failing if a index is not available.
* include_global_state: defaults to true, it will store index templates and persistent cluster setting from the cluster state. This can be helpful if you want to recreate a cluster of if you want to migrate your indices.
* partial: defaults to false; It stores empty or corrupted shards as well instead of failing the backup. During a restore it will creates missing shards as empty once.

