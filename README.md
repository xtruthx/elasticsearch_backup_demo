# Tutorials for a snapshot and restore of a index

This are the steps from the Demo during the talk about "Restore and Backup of Elasticsearch Indices".

Please note that there many pitfalls and minimum knowledge of Elasticsearch are required to obtain a valid backup cycle.

This Repository has the focus on some important curl API Requests and provides to Curator Examples.

## Content

1. [Repository](01_repository/README.md)
2. [Snapshot](02_do_snapshots/README.md)
3. [Restore](03_restore/README.md)
4. [Progress](04_progress/README.md)
5. [Curator](05_curator/README.md)

## References

* [Doing Snapsnhot and Restore Elasticsearch Documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-snapshots.html)
* [Elastic Curator Documentation](https://www.elastic.co/guide/en/elasticsearch/client/curator/current/index.html)
* [Elasticsearch Curator API](https://curator.readthedocs.io/en/latest/)

## Hint on "bug" in Curator version 5.5.4

* [#1234](https://github.com/elastic/curator/issues/1243)

In virtual environments like kvm, virtualbox, docker  (hits me in actual CentOS 7 and Debian 9) the "LC_ALL" is unset.
Curator needs that locale to be set with a UTF-8 locale. 
