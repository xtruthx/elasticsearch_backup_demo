## Restore a snapshot

The default will restore all indices in a snapshot

`
curl -X POST "localhost:9200/_snapshot/my_backup/snapshot_1/_restore"
`


## Advanced restore

It is possible to restore specific indices from a snapshot with a given name. You also have the option to use a restore for different purposes
and to implement a automation. It is also possible to rename indices or to reduce replicas or to restore the cluster state too.

`
curl -X POST "localhost:9200/_snapshot/nfs_repoistory/snapshot_name/_restore" -H 'Content-Type: application/json' -d'
{
  "indices": "index_1,index_2",
  "include_global_state": true,
  "rename_pattern": "index_(.+)",
  "rename_replacement": "restored_index_$1",
  "partial": true
}
'
`

* indices: Restore specific indices
* rename_pattern:  defines what should be  automatically renamed
* rename_replacement: defines the name  with a variable which will  be appended with the match from the pattern
* include_global_state:  defaults to false. If set to true it will also restore templates and cluster settings and it will also overrides existing once

## Partial Restore option

If you restore a partial snapshot you need to use partial set to true. Default is to false. That makes it possible to migrate or restore corrupted indices.
