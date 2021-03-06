# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## 2.2.0 (2019-04-29)
### Added
- Upgraded to SDK v3.1.5. This version implements [the aget/integrations
  protocol v3](https://github.com/newrelic/infra-integrations-sdk/blob/cb45adacda1cd5ff01544a9d2dad3b0fedf13bf1/docs/protocol-v3.md),
  which enables [name local address replacement](https://github.com/newrelic/infra-integrations-sdk/blob/cb45adacda1cd5ff01544a9d2dad3b0fedf13bf1/docs/protocol-v3.md#name-local-address-replacement).
  and could change your entity names and alarms. For more information, refer
  to:
  
  - https://docs.newrelic.com/docs/integrations/integrations-sdk/file-specifications/integration-executable-file-specifications#h2-loopback-address-replacement-on-entity-names
  - https://docs.newrelic.com/docs/remote-monitoring-host-integration://docs.newrelic.com/docs/remote-monitoring-host-integrations 

## 2.1.0 (2019-04-08)
### Added
- Remote monitoring option. It enables monitoring multiple instances, 
  more information can be found at the [official documentation page](https://docs.newrelic.com/docs/remote-monitoring-host-integrations).

## 2.0.3 (2018-12-04)
### Added
- Fix bug that made db.keyspace, db.columnFamily,db.keyspaceAndColumnFamily to be filled with default values.

## 2.0.2 (2018-09-12)
### Added
- Fix `integrationVersion` field for cassandra integration.

## 2.0.0 (2018-09-6)
### Added
- Updated SDK to v3.
- Cache collision bug fixed.

## 1.2.0 (2018-07-11)
### Added
- Add threadpool and histogram metrics

## 1.1.0 (2017-10-16)
### Added
- Set column families limit as a configurable value
- Set query timeout as a configurable value

## 0.1.0
### Added
- Initial release, which contains inventory and metrics data
