# PySpark

### Differences between SparkContext and SparkSession in PySpark

When working with Apache Spark through PySpark, two fundamental objects are often used: `SparkContext` and `SparkSession`. While they might seem similar, they serve different purposes and have distinct roles within the Spark ecosystem.

#### SparkContext

1. **Core Entry Point**: `SparkContext` is the original entry point for Spark functionality. It allows the Spark application to access Spark's cluster services and to run jobs.
2. **RDD API**: It provides the primary interface for working with low-level Resilient Distributed Datasets (RDDs), which are the core data structure of Spark.
3. **Configuration**: `SparkContext` is configured using a `SparkConf` object, where you can set various Spark parameters and settings before creating the context.
4. **Backward Compatibility**: It has been part of Spark since its early versions and is essential for operations that directly manipulate RDDs.

#### SparkSession

1. **Unified Entry Point**: Introduced in Spark 2.0, `SparkSession` acts as the single entry point to Spark and integrates the functionality of `SQLContext` and `HiveContext` along with `SparkContext`. It simplifies the APIs.
2. **Higher-level API**: It provides a higher-level API for working with structured data, including DataFrames and Datasets, which are easier to use and more optimized than RDDs.
3. **SQL and DataFrames**: `SparkSession` enables the use of SQL queries directly on DataFrames and integrates with Hive, allowing for a more streamlined workflow when working with structured data.
4. **Creation and Management**: It is typically created using the `builder` pattern, which allows for more flexible configuration compared to `SparkContext`.

Here’s a quick comparison to summarize:

| Feature                  | SparkContext                                       | SparkSession                                      |
|--------------------------|----------------------------------------------------|---------------------------------------------------|
| Introduction             | Original entry point                               | Introduced in Spark 2.0                           |
| Primary Use              | Low-level RDD API                                  | High-level APIs with DataFrames and SQL           |
| Integration              | Basic functionality, needs `SQLContext` or `HiveContext` for SQL support | Unified interface for Spark, SQL, and Hive         |
| Configuration            | Via `SparkConf` object                             | Via `builder` pattern                             |
| Optimization             | Less optimized for SQL and structured data         | Optimized query execution and Catalyst optimizer  |

In practice, for new Spark applications, it's recommended to use `SparkSession` as it provides a more unified and easier-to-use interface for working with Spark's capabilities.


---
