# owlsim-v3

Ontology Based Profile Matching

[![Build Status](https://travis-ci.org/cmungall/owlsim-v3.svg)](https://travis-ci.org/cmungall/owlsim-v3)
[![Coverage Status](https://coveralls.io/repos/cmungall/owlsim-v3/badge.svg)](https://coveralls.io/r/cmungall/owlsim-v3)

This will eventually replace sim2 currently distributed as part of owltools

## Documentation

For now you must do this:

    mvn javadoc:javadoc

And then open target/site/apidocs/index.html in a browser

## Running it

To become more familiar with the code, please run the junit tests in eclipse.

Also try the performance/integration tests in `owlsim.compute.matcher.perf` - these will need extra files downloaded
see the Makefile for details.

To run the REST services:

    mvn package

produces a standalone Dropwizard jar:

    owlsim-services/target/owlsim-services-3.0-SNAPSHOT.jar

which runs with:

    java -jar owlsim-services/target/owlsim-services.3.0-SNAPSHOT.jar server configuration.yaml

where configuration.yaml describes the desired ontologies:

    ontologyUris:
      - owlsim-core/src/test/resources/species.owl
    ontologyDataUris: []

and then browse the [REST documentation](http://localhost:8080/api/docs/).

If you prefer to run the REST services from your IDE launch:
`org.monarchinitiative.owlsim.services.OwlSimServiceApplication` as a main
class with `server` and an appropriate YAML configuration as arguments.
