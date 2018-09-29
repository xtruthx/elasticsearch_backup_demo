## List all snapshots from a repository

You can retrieve a list of snapshots in a repository. This can be used in scripts for maintaining snapshots like the retention e.g.

`
curl -X GET "localhost:9200/_snapshot/nfs_repoistory/_all
`
or for a single index

`
curl -X GET "localhost:9200/_snapshot/nfs_repoistory/*_snapshotname
`

You can also search for snapshots with wildcards. The output is json formatted in both cases.
