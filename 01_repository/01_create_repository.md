## First we create the repository in the cluster

If you have configured the path of your fs-mount on all your Elasticsearch nodes, you need to register this 
repository for creation:
`
curl -X PUT "localhost:9200/_snapshot/nfs_repository" -H 'Content-Type: application/json' -d'
{
  "type": "fs",
    "settings": {
        "location": "/elasticdata/backup"
	"compress": true
     }
}'
`

You configure the repository with compression or without at that point. Other options like setting a max transfer rate in bytes for reading and writing are also possible.

