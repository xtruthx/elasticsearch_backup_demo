# Verification of the repository

You should at least verify once if the repository was successfully created on all nodes in the cluster:

`
curl -X POST "localhost:9200/_snapshot/nfs_repository/_verify"
`
