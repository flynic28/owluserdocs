---
description: Validate data between distinct storage systems
---

# Copying or Moving data

## Record-for-Record Reconciliation

When you’re copying or moving data between distinct storage systems such as multiple HDFS clusters or between non-HDFS storage and cloud storage, it’s a good idea to perform some type of validation to guarantee data integrity. This validation is essential to be sure data wasn’t altered during transfer.

### Common Data Copying/Movement Scenarios 

* Landing, Loading, Persisting third-party files
  * Landing daily files. 
  * Loading daily files into staging location. 
  * Finally, persisting data in lake or warehouse.
* Cloud Migrations  
  * Between existing database storage to optimized cloud storage formats.
  * Between local file systems and cloud relational database 
* Data Lake or Data Warehouse
  * Migrating data from single storage system to distributed storage
  * Consolidating storage systems to a single lake or warehouse
* Same Storage, Different Environments 
  * Copying same data between Dev, QA, and Prod environments.

#### _How do you easily validate the same data exists in distinct locations?_ 

{% hint style="info" %}
 Low-level integrity checks like row counts and column counts are not sufficient.
{% endhint %}

Detect potential data corruption caused, for example, by older versions of drivers, noisy network links, memory errors on server computers and routers along the path, or software bugs \(such as in a library that customers use\).

### Shortcomings of Existing Validation Checks

* No easy way to reconcile between across non-HDFS files and database.
* Chunk verification requires storage size, format, and metadata to be exactly equal.
* Different data types in two distinct databases \(Oracle and Teradata\) will not reconcile.
* Two different copies of the same files in HDFS, but with different per-file block sizes configured.
* Two different instances of HDFS with different block or chunk sizes configured.
* Copying across non-HDFS [Hadoop-compatible file systems](https://wiki.apache.org/hadoop/HCFS)
* https://wiki.apache.org/hadoop/HCFS
* \(HCFS\) such as Cloud Storage.

Explicit end-to-end data integrity validation adds protection for cases that may go undetected by typical in-transit mechanisms. 

### Enter, OwlDQ Integrity Validation!

To ensure and protect against target systems getting out of sync or not matching the originating source, turn on `-vs` to validate that the source matches the target. [Read More](https://docs.owl-analytics.com/dq-visuals/validate-source)

{% embed url="https://docs.owl-analytics.com/dq-visuals/validate-source" %}

Complete row, column, conformity, and value checks between any two distinct storage systems. Can be run against high-dimension or low-dimension datasets. Works against Files and/or Database storage, On-premise, or across Cloud environments. 

You have a lot going on: deadlines, ongoing projects on the back-burner, and friends and family to boot.

OwlDQ has forged ahead, dealing with all the boilerplate code so you don’t have to.

We don’t want you to get stuck writing a bunch of integrity checks we’ve already written!  Focus on other stuff that actually moves your project forward.










