Keep development, staging, and production as similar as possible

All environments should be as similar as possible.

This reduces the number of bugs and downtime and allows your organization to have a much more rapid development cycle.

There have been substantial gaps between development (a developer making live edits to a local deployment of the app) and production (a running deployment of the app accessed by end users). These gaps manifest in three areas:

    The time gap: A developer may work on code that takes days, weeks, or months to go into production.

    The personnel gap: Developers write code, and ops engineers deploy it.

    The tools gap: Developers may use a stack like Nginx, SQLite, and OS X, while the production deployment uses Apache, MySQL, and Linux.

and it looks like this:

<img src="images\image-6.png" alt="gap on tools and process">

The twelve-factor app is designed for continuous deployment by keeping the gap between development and production small.

The twelve-factor developer resists the urge to use different backing services between development and production.

So with continuous integration and continuous delivery and deployment tools, today we can reduce the time. It takes from changes to go from dev to production env in a matter of hours or even to a matter of minutes in some cases. The developer who writes code should also be involved in deploying and watching it in the production environment and with tools. We must aim to keep the same tools as much as possible with more than tools being lightweight and containerization tools like Docker making it to easy set up dev env. This shouldn't be hard to achieve. 

<img src="images\image-7.png" alt="closing gap and keep it the same process">
