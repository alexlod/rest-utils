Confluent REST Utils
====================

Confluent REST Utils provides a small framework and utilities for writing Java
REST APIs using Jersey, Jackson, Jetty, and Hibernate Validator.

See the [`examples/`](examples/) directory for a simple demo service.

Security
--------
The REST `Application` can support both HTTP and HTTPS. HTTPS is disabled by default. Three modes are supported:
http, https, and http+https. In the last mode, http and https are supported on different ports.

The HTTPS implementation is similar to Kafka, where the server specifies a keystore and trust store. When the SSL
client auth is configured, the client must authenticate -- the key in the client's keystore must be trusted by
the server's trust store, either because the client cert is in the server's trust store, or because the CA that signed
the client's cert is in the server's trust store.

Metrics
-------
When both http and https protocols are enabled, two metrics groups are created, `jetty-metrics` and
`jetty-https-metrics`. However, `jetty-https-metrics` is a duplicate of `jetty-metrics`. Put differently, each
metrics group will have the same value for all metrics, and those values will be influenced by both http and
https requests.

Contribute
----------

- Source Code: https://github.com/confluentinc/rest-utils
- Issue Tracker: https://github.com/confluentinc/rest-utils/issues

License
-------

The project is licensed under the Apache 2 license.
