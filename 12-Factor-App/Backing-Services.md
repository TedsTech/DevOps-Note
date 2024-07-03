Treat backing services as attached resources

All backing services are treated as attached resources and attached and detached by the execution environment.

For example, your development environment talks to a MySQL server on your local machine. On production, your database runs on another server. The only difference will be the URL to connect to in the configuration.

Resources can be attached to and detached from deploys at will. For example, if the app’s database is misbehaving due to a hardware issue, the app’s administrator might spin up a new database server restored from a recent backup. The current production database could be detached, and the new database attached – all without any code changes.