## Status
considering

## Context
starting to generate a bunch of data, ~1 GB

want to periodically store this somewhere off-site for DR

## Decision

scheduled task to:  

    generate database dump and store locally
    upload database dump to S3

manually invoked task to:  

    get database dump from cloud and store it locally
    make local database state match local backup file state

## Consequences
### good
- easy cost control with s3 versioning
- simple impl: basically just gluing together execution of `postgres` cli using official postgres docker image 

### bad
- giving amazon my IP