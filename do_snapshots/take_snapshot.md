## Take a snapshot of all indices

curl -X PUT "localhost:9200/_snapshot/nfs_repository/snapshot_1?wait_for_completion=true"


## Advanced Snapshot settings from specific indices

curl -X PUT "localhost:9200/nfs_snapshot/my_backup/snapshot_2?wait_for_completion=true" -H 'Content-Type: application/json' -d'
{
  "indices": "index_1,index_2",
  "ignore_unavailable": true,
  "include_global_state": false,
  "partial": true
}
'

### Explained Settings

* ignore_unavailable: 
* include_global_state: defaults to true, it will store templates and persistent setting from the cluster state asswell
* partial: defaults to false; It stores empty or corrupted shards as well instead of failing the backup. During a restore it will creates missing shards as empty once.

