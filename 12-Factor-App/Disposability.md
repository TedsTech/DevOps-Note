Maximize robustness with fast startup and graceful shutdown

The twelve-factor app’s processes are disposable, meaning they can be started or stopped at a moment’s notice. 

The twelve-factor app's processes should shutdown gracefully when they reveive a SIGTERM  signal from the process manager. 

Fast startup and shutdown are advocated for a more robust and resilient system.

For example, with a retail website, in the case of failure of a process of order-service, the user should still be able to access the website and eventually within no time should be able to order immediately.

Here is the one of the example:

<img src="images\image-5.png" alt="codebase-Deploys">