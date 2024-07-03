Execute the app as one or more stateless processes

Twelve-factor processes are stateless and share-nothing.

Data that must be persistent should be stored in a stateful backing service.

Applications should be deployed as one or more stateless processes with persisted data stored on a backing service.

    For example, if a part of your application stack fails, the app itself does not become a failure.