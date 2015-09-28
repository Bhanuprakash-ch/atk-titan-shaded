# atk-titan-shaded
Both Titan and Spark depend on Kryo. This causes a ClassLoader conflict when Titan tries
to use Kryo after it has already been initialized by Spark.

This build creates an uber jar containing titan-core and kryo where kryo has been moved
to a new package to prevent ClassLoader conflicts with Spark.

This artifact can be used just like titan-core except that you must include the direct
dependencies for titan-core manually.
