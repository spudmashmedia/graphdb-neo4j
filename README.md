# GraphDB-Neo4j

A Neo4j Instance inside a VirtualBox image using Docker

Tools used:

- Neo4j Graph DB <https://registry.hub.docker.com/u/kbastani/docker-neo4j/>



## Prerequisites

1. Virtual Box (box: ubuntu/trusty64)
2. Vagrant

## Installation

1. Clone this repo
2. vagrant up

Note: if the build fails half way thru building, try "vagrant reload --provision" to retry.

## Usage

| Tool | Host URL<br> (navigate in your browser) |
|------|--------------|
| GraphDB| http://127.0.0.1:7474 |


## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

| Date | Version | Description|
|-------|----------|-------------|
|2015-07-21 | 1.0 | initial version

## Credits

<http://neo4j.com><br/>
<https://registry.hub.docker.com/u/kbastani/docker-neo4j/>


GraphDB-Neo4j is made available under the MIT license.
<http://opensource.org/licenses/MIT>

Copyright (c) 2015 Spudmash Media Pty Ltd
