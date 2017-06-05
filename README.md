# django-mpathy

*NOTE: This software is _pre-alpha_ and will change a lot very quickly. Don't use it yet.*

mpathy is a Materialised Path implementation for django. Use it for storing hierarchical data in your postgres database,
and accessing it from Django.

It is a fairly thin wrapper around Postgres' [ltree extension](https://www.postgresql.org/docs/current/static/ltree.html)

# Why

There are a few existing ways to store trees in databases via Django. The main two libraries are:

* django-mptt (implementation of MPTT / "nested sets")
* django-treebeard (multi-backend tree storage app)

While both are good and widely used, both suffer from a large amount of complexity, both in implementation and interface.

The need to support multiple database backends, as well as the lack of well-indexed database tree implementations at the time they were created, has made both projects overly complex.

# Goals

mpathy intends to:
 * only support Postgres. I have no interest in supporting MySQL.
 * only support materialised path. The other implementations are too complicated, and the benefits are fairly small.
 * Push most of the work into the database to ensure performance and consistency.
 * Leverage modern django and postgres features to keep the code tidy and performant.