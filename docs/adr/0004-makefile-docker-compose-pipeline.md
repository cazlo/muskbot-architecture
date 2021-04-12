## Status
accepted

## Context
want to setup foundational stuff in the build/test/deploy pipeline
to facilitate move to cloud later on.

docker is a good way to avoid machine specific dependencies.

docker-compose can easily spin up swarms of components

## Decision

use makefile and docker-compose to manage service spin up and tear down
organize components by directory e.g.

    muskbot
        Readme.md
        Makefile
        component1
            Makefile
            package.json
        .....
        componentN
            Manefile
            package.json

## Consequences
### good
- easy to move to cloud based container orchestration in future
- foundational work for build/test pipeline automation in future

### bad
- lots of glue