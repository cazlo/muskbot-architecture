## Status
accepted

## Context
there will be a bunch of components which are interconnected and all requring DB access for some reason or other



## Decision

keep all components of muskbot in single repo

organize components by directory e.g.

    muskbot
        Readme.md
        component1
            package.json
        .....
        componentN
            package.json

make sure components are as isolated as possible and only using shared stuff if necessary

## Consequences
### good
- individual scalability of services
- encourages code re-use through libs-as-directories pattern
- easy service splitout later if necessary
- very easy to spin the whole thing up locally and use it
- the whole machine is in your IDE so chances of string searching success and IDE magic based on string searching is high

### bad
- lots of stuff for IDE to load -> big memory footprint of IDE