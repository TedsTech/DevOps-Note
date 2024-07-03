Export services via port binding

The twelve-factor app is completely self-contained and does not rely on runtime injection of a webserver into the execution environment to create a web-facing service.

Web apps are often executed inside webserver containers.

Apps are completely self-contained and don't rely on runtime injection of a webserver into the execution environment to create client-facing services.
    Services export their native protocol by binding a port and listening for traffic on it.
Routing differs:
    Local development environments just use ports on localhost.
    Production environments have some kind of API gateway for this.

This enables one app to be a backing service for another by referencing it in the consuming app's Configuration.

For example, Spring boot by default comes with embedded tomcat, jetty, or undertow.