Keep development, staging, and production as similar as possible

All environments should be as similar as possible.

This reduces the number of bugs and downtime and allows your organisation to have a much more rapid development cycle.

There have been substantial gaps between development (a developer making live edits to a local deploy of the app) and production (a running deploy of the app accessed by end users). These gaps manifest in three areas:

    The time gap: A developer may work on code that takes days, weeks, or even months to go into production.

    The personnel gap: Developers write code, ops engineers deploy it.

    The tools gap: Developers may be using a stack like Nginx, SQLite, and OS X, while the production deploy uses Apache, MySQL, and Linux.

and it's look like this:

<img src="images\image-6.png" alt="gap on tools and process">

The twelve-factor app is designed for continuous deployment by keeping the gap between development and production small.

The twelve-factor developer resists the urge to use different backing services between development and production.

So with continuous integration and continuous delivery and deployment tools, today we are able to reduce the time. It takes from changes to go from dev to production env in a matter of hours or even to a matter of minutes in some cases. The developer who writes code should also be involved in deploying and watch it in production env and with tools. We must aim to keep the same tools as much as possible with more than tools being lightweight and containerization tools like Docker makinng it to easy set up dev env. his should't be hard to acheive. 

<img src="images\image-7.png" alt="closing gap and keep it same process">