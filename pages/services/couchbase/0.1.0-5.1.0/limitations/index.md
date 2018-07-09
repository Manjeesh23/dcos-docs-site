---
layout: layout.pug
navigationTitle:  Limitations
title: Limitations
menuWeight: 110
excerpt: Understanding configuration Limitations
featureMaturity:
enterprise: false
---

## Out-of-band configuration

Out-of-band configuration modifications are not supported. The service's core responsibility is to deploy and maintain the service with a specified configuration. In order to do this, the service assumes that it has ownership of task configuration. If an end-user makes modifications to individual tasks through out-of-band configuration operations, the service will override those modifications at a later time. For example:

- If a task crashes, it will be restarted with the configuration known to the scheduler, not one modified out-of-band.
- If a configuration update is initiated, all out-of-band modifications will be overwritten during the rolling update.

## Scaling in

To prevent accidental data loss, the service does not support reducing the number of pods but can increase the number of pods.

## Disk changes

Full, Cluster, and Bucket Administrators can edit a subset of the settings already established on an existing bucket. 

## Best-effort installation

If your cluster doesn't have enough resources to deploy the service as requested, the initial deployment will not complete until either those resources are available or until you reinstall the service with corrected resource requirements. Similarly, scale-outs following initial deployment will not complete if the cluster doesn't have the needed available resources to complete the scale-out.

## Virtual networks

When the service is deployed on a virtual network, the service may not be switched to host networking without a full re-installation. The same is true for attempting to switch from host to virtual networking.

## Task Environment Variables

Each service task has some number of environment variables, which are used to configure the task. These environment variables are set by the service scheduler. While it is possible to use these environment variables in adhoc scripts (e.g. via `dcos task exec`), the name of a given environment variable may change between versions of a service and should not be considered a public API of the service.

## Installation Limitations

### PreinstallNotes 

For a couchbase cluster with 2 data node, 1 index node, 1 query node, and 1 full text search node you need a dc/os cluster with 5 private agents.

The recommended hardware specifications to install and effectively operate Couchbase Server include:

Four core 64-bit x86 CPU running at 3GHz; six cores when using Cross Datacenter Replication (XDCR) and Views.
16GB RAM (physical).
A local block-based storage device (hard disk, SSD). Network filesystems such as CIFS and NFS are not supported.

### Storage 
Couchbase Server consists of various services and components that have different storage requirements. Each component uses the optimized storage engine purpose-built and configured for the workload of relevant components.

Data Service, MapReduce Views, Spatial Views, and Couchstore
For core data operations, MapReduce views, and spatial views, Couchbase Server uses Couchstore. Each vBucket is represented as a separate Couchstore file in the file system. Couchstore uses a B+tree structure to quickly access items through their keys. 

Index Service, Search Service, and ForestDB
For indexing with GSI in the Index service and full-text index in the search service, Couchbase Server uses ForestDB. With ForestDB, each index is represented as a separate ForestDB file in the file system. Unlike Couchstore, ForestDB uses a B+trie structure to quickly access item through its index key. B+trie provides a more efficient tree structure compared to B+trees and ensures a shallower tree hierarchy to better scale large item counts and very large index keys.

### Backup
cbbackupmgr Tool
The cbbackupmgr tool is a utility to help manage and store backup and recovery data on disk for your Couchbase Server. It backs up and restores bucket data, views creation scripts, index creation scripts, bucket configurations, and so on. Backups are stored in an Archive Repository that contains each backup.
