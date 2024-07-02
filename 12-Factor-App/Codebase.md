One codebase tracked in revision control, many deploys

The twelve-factor app is always tracked in a version control system, such as Git and so on.

Note:
If there are multiple codebases, it’s not an app – it’s a distributed system. Each component in a distributed system is an app, and each can individually comply with twelve factors.

Multiple apps sharing the same code is a violation of the twelve-factor. The solution here is to factor shared code into libraries which can be included through the dependency manager.

For example:
            Here is the Codebase
                        .                   .               .               .
                        .                   .               .               .
                        .                   .               .               .
                        .                   .               .               .
            Deploys     Production          Staging         Dev-1           Dev-2

<img src="image.png" alt="codebase-Deploys">


Here is another example of having a codebase help resolve the issue. This is very common practice on DevOps now.

This X company had only one developer and they have successfully deployed the website or web app. Later on, X company needs to hire a few more developers and they all are working on their own development environment but on the same code base and they're all copying their code from a central hub whenever they are ready. Now they are on each other toes working on the same files at the same time and creating conflicts. Now company X needs a solution to resolve this issue so they can help collaborate and that's where git comes in. Git helps all developers to work on the same application at the same time and collaborate efficiently. However, now everyone has installed and configured git on their machines which is going to help in easily pulling the latest code from the central hub using the poll comment "git pull" and they add changes that can push it to the hub using "git push". The central hub is a cloud-based platform that serves as the central location of all code.

Having multiple application services is no longer having a single app instead you have a distributed system and as per the 12-factor app, sharing the same code is a violation of the 12-factor. Matter of fact it should be separated into its codebases.
