# Accumulo

## Python Integration

There's a python package written by the NSA that allows Python 3 applications to integrate with Apache Accumulo called `accumulo-python3`.

This provides classes for creating accumulo objects (such as mutations and ranges), a blocking, synchronous client, and a non-blocking, asynchronous client for applications using the asyncio module.

This module is not on the pip install list yet, and is a work in progress. It can be pulled from right now though.

This can be integrated with Spark, which may make Accumulo accessible through pyspark.

## Overview

This is an open source implementation of Google BigTable system for a distributed storage system for structured data.

Accumulo has a key-value data model instead of a columnar data model, which allows applications to control data format and layout. This allows developers to make more decisions about data storage to make accessing data more efficient.

Accumulo sorts data by Key, and then distributes them across commodity class servers.

This is good choice for apps that serve requests coming from a large number of users to access data from a any size of data without changing the application logic.

It is designed to run on commodity class servers rather than one expensive single server. And is really quick as opposed to expensive large disk systems.

Accumulo is designed to process a user request in milliseconds by doing a binary search, then a sequential read of the next key value pairs and return those to the user.

As the app designer, you have complete control over how the data is sorted to access the data quickly and efficiently.

This is great for when data size far exceeds the size of data that can be stored in memory, and when data access patterns are simple enough to be performed over many servers.

### Other features

Accumulo can apply security labels to each key-value pair to make certain data tougher to access to protect data from unauthorized access.

The ability to perform parallel reads to read a second index efficiently.

Also has iterators to be able to perform queries in parallel instead of by just one client.

Also has automatic hardware recovery, automatic load balancing, and dynamically allows for unlimited columns.

Accumulo is written in Java and integrates with Spark, and has a proxy to allow other langauges to interact with Accumulo as well.
