# ElasticSearch

Elasticsearch is a highly scalable open-source full-text search and analytics engine. It allows you to store, search, and analyze big volumes of data quickly and in near real time.

# Basic Concepts

There are a few concepts that are core to Elasticsearch.

## NRT

Elasticsearch is a near real time search platform. What this means is there is a slight latency (normally one second) from the time you index a document until the time it becomes searchable.

## Cluster

A cluster is a collection of one or more nodes (servers) that together holds your entire data and provides federated indexing and search capabilities across all nodes. A cluster is identified by a unique name which by default is "elasticsearch". This name is important because a node can only be part of a cluster if the node is set up to join the cluster by its name.

## Node

A node is a single server that is part of your cluster, stores your data, and participates in the cluster’s indexing and search capabilities. A node is identified by a name which by default is a random Universally Unique Identifier (UUID) that is assigned to the node at startup. Different type of nodes

- **Master Node**: Use for creating/deleting index, tracking which node are part of cluster, deciding which shards allocate to which node.
- **Data Node:** It hold data and perform data related operations such as CRUD, search, and aggregations.
- **Ingest Node:** To transform and enrich the document before indexing. 
- **Tribe Node:** it can connect to multiple clusters and perform search and other operations across all connected clusters.

## Index

An index is a collection of documents that have somewhat similar characteristics. For ex: Product catalog, Customer information, Order etc...

## Type

Deprecated in 6.0.0. A type used to be a logical category/partition of your index to allow you to store different types of documents in the same index, eg one type for users, another type for blog posts.

## Document

A document is a basic unit of information that can be indexed.

## Shards and Replicas

Dividing index into multiple parts know as **shards**. Each shard is in itself a fully-functional and independent "index" that can be hosted on any node in the cluster. Sharding is important for two primary reasons:

- It allows you to horizontally split/scale your content volume
- It allows you to distribute and parallelize operations across shards (potentially on multiple nodes) thus increasing performance/throughput.

For failover, elasticsearch allow you to make one or more copies of shards known as **replicas**

Replication is important for two primary reasons:

- It provides high availability in case a shard/node fails. 
- It allows you to scale out your search volume/throughput since searches can be executed on all replicas in parallel.

## Reference

https://www.elastic.co/guide/en/elasticsearch/reference/current/getting-started.html

https://www.elastic.co/guide/en/elasticsearch/reference/current/_basic_concepts.html

https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-node.html