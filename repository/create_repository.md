## First we create the repository in the cluster

curl -X PUT "localhost:9200/_snapshot/nfs_repository" -H 'Content-Type: application/json' -d'
{
  "type": "fs",
    "settings": {
        "location": "/eelasticdata"
	"compress": true
     }
}'

