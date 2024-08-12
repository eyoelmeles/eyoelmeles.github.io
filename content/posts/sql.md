---
title: "Sql"
date: 2024-05-14T19:18:08+08:00
draft: true
---

# Structured Query Language

DDL:
DML:

    Any modification the DML statement makes to the database is *transaction*
    Transactions made by the DML should then be controlled,
    They will be controlled by Transaction Control Language

    TCL:

HADOOP File System (HDFS)
master slave nodes,

- devide files into blocks, for easy read and write
- replicate blocks for fault tolerance

* HeartBeat: slave nodes send signals to the master node to check if they still are represented
* Balancing: if slave crashes, master will give signal to the other datanodes to replicate until replication factor is met.

MasterNode (NameNode):
_ manage all slave nodes and assign task to them,
_ execute file operations(open, close, rename, change directory)

- store metadata

DataNode (SlaveNode):

- work with the files (read, write, processing)
- create, delete and replicate files if asked by the MasterNode
- Require high memory as data is actually stored here
- reponsible for replications on command
