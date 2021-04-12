## Status
accepted

## Context
Need some way to store system state for analysis.

Postgres SQL is good for storing relational data in an optimized way.

If you can fit the entire DB in memory, reads are very fast.

JSONb support is somewhat quick and very easy for non-homogenous data types (e.g. job configurations)

You can spin up a db locally using docker.

There are decades of existing tooling and documentation to leverage with most SQL stuff.

## Decision

spin up a local postgres docker image locally

use a volume mount to ensure database state is preserved between restarts of host machine/docker.

## Consequences
### good
- cheap
- reasonably quick

### bad
- database limited in how much memory and CPU it can access