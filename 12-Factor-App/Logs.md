Treat logs as event streams

Logs provide visibility into the behavior of a running app. In server-based environments they are commonly written to a file on disk (a “logfile”); but this is only an output format.

A twelve-factor app never concerns itself with routing or storage of its output stream.

Store logs in a centralized location in a structured format

Logs provide insight into a running app's behaviour.

Streams of aggregated, time-ordered events collected from output streams of Processes and Backing services.

    Raw form is typically text.

    We can mutate them into more structured data formats.

    No fixed beginning or end.

Apps don't concern themselves with the routing or storage of their output.

    They write to stdout.

    Local execution during development allows developers to see the logs via their terminal.

In deployed environments we can capture and retain this stream.

    Logstash

    p.r.comp.log.fluentd (Private)

The event stream is handled by the deployment environment, enabling:

    Finding historical events.

    Graphing trends.

    Active alerting.

Here is the example of logs streams:

  <img src="images\image-8.png" alt="logs">