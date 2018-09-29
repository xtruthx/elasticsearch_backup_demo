## Considerations about a restore

* If you restore a indices the number of primary and replica shards must be fit into the actual cluster,
  otherwise you will end in a yellow state
* If you restore a index with shard allocation attributes the also must be configured on the actual Elasticsearch
  nodes in the cluster
* If you restore a index in the cluster you want to restore should be in the state closed. It will be reopened and is online
  after the restore. If the index is not present it will be recreated.
* If you restore a index or hole snapshot with "include_global_state: true" you should be consider that your actual templates if they
  exist will be overwritten and the cluster settings too.
