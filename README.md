# New Relic Infrastructure Integration for Cassandra
New Relic Infrastructure Integration for Cassandra captures critical performance metrics and inventory reported by Cassandra server.

<!---
See [metrics]() or [inventory]() for more details about collected data and review [dashboard]() in order to know how the data is presented.
--->

## Requirements
* Apache Cassandra 3.x

## Configuration
It is required to configure the JMX user and password. Follow the steps in [Enabling JMX authentication and authorization](http://docs.datastax.com/en/cassandra/3.0/cassandra/configuration/secureJmxAuthentication.html) for more details.

## Installation
* Download an archive file for the Cassandra Integration
* Place the executables under `bin` directory and the definition file `cassandra-definition.yml` in `/var/db/newrelic-infra/newrelic-integrations`
* Set execution permissions for the binary files `nr-cassandra` and `nrjmx` (if required)
* Place the integration configuration file `cassandra-config.yml.sample` in `/etc/newrelic-infra/integrations.d` and update its values.

## Usage
This is the description about how to run the Cassandra Integration with New Relic Infrastructure agent, so it is required to have the agent installed (see [agent installation](https://docs.newrelic.com/docs/infrastructure/new-relic-infrastructure/installation/install-infrastructure-linux)).

In order to use the Cassandra Integration it is required to configure `cassandra-config.yml.sample` file. Firstly, rename the file to `cassandra-config.yml`. Then, depending on your needs, specify all instances that you want to monitor. Once this is done, restart the Infrastructure agent.

You can view your data in Insights by creating your own custom NRQL queries. To
do so use **CassandraSample** or **CassandraColumnFamilySample** event types.

## Integration development usage
Assuming that you have source code you can build and run the Cassandra Integration locally.
* Go to directory of the Cassandra Integration and build it
```bash
$ make
```
* The command above will execute tests for the Cassandra Integration and build an executable file called `nr-cassandra` in `bin` directory.
```bash
$ ./bin/nr-cassandra --hostname <JMX hostname> --port <JMX port> --username <username> --password <password> --config_path <path to cassandra config>
```
* If you want to know more about usage of `./bin/nr-cassandra` check
```bash
$ ./bin/nr-cassandra --help
```

For managing external dependencies [govendor tool](https://github.com/kardianos/govendor) is used. It is required to lock all external dependencies to specific version (if possible) into vendor directory.

## Running on a containerized agent

If you are running this integration in a [containerized agent](https://hub.docker.com/r/newrelic/infrastructure/), you should use a version greater than 0.0.26, otherwise the integration could yield `defunct` processes.

## Contributing Code

We welcome code contributions (in the form of pull requests) from our user
community. Before submitting a pull request please review [these guidelines](https://github.com/newrelic/nri-cassandra/blob/master/CONTRIBUTING.md).

Following these helps us efficiently review and incorporate your contribution
and avoid breaking your code with future changes to the agent.

## Custom Integrations

To extend your monitoring solution with custom metrics, we offer the Integrations
Golang SDK which can be found on [github](https://github.com/newrelic/infra-integrations-sdk).

Refer to [our docs site](https://docs.newrelic.com/docs/infrastructure/integrations-sdk/get-started/intro-infrastructure-integrations-sdk)
to get help on how to build your custom integrations.

## Support

You can find more detailed documentation [on our website](http://newrelic.com/docs),
and specifically in the [Infrastructure category](https://docs.newrelic.com/docs/infrastructure).

If you can't find what you're looking for there, reach out to us on our [support
site](http://support.newrelic.com/) or our [community forum](http://forum.newrelic.com)
and we'll be happy to help you.

Find a bug? Contact us via [support.newrelic.com](http://support.newrelic.com/),
or email support@newrelic.com.

New Relic, Inc.
