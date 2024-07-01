One codebase tracked in revision control, many deploys

The twelve-factor app is always tracked in a version control system, such as Git and so on.

Note:
If there are multiple codebases, it’s not an app – it’s a distributed system. Each component in a distributed system is an app, and each can individually comply with twelve-factor.

Multiple apps sharing the same code is a violation of twelve-factor. The solution here is to factor shared code into libraries which can be included through the dependency manager.

For example:
            Here us the Codebase
                        .                   .               .               .
                        .                   .               .               .
                        .                   .               .               .
                        .                   .               .               .
            Deploys     Production          Staging         Dev-1           Dev-2

<img src="image.png" alt="codebase-Deploys">


Here is the another example of having a codebase help resolve the issue. This is very comman practice on DevOps now.

This X compnay had only one developer and they have successfuly deploy the website or web app.Later on X compnay need to hire few more developer and they all are working on their own development environment but on same code base and they're all copying their code from a central hub whenever they are ready. Now they are on each other toes working on the same files at the same time and creating conflicts. Now conpnay X need a solution to resolve this issue so they can help collaborate and that's where git come in. Gut help all developers to work on the same application at the same time and collaborate efficiently. However, now every one intall and configures git on there machines and going to help in easily pulling the latest code from the central hub using the poll commant "git pull" and they add chnages can push it to the hub using "git push". The central hub is a cloud-base platform that serves as central location of all code. 

Having a multiple application services is no longer having a single app insted you have a distributed system and as per the 12 factor app, sharing the saem code is a violation of the 12 factor. Mater of fact it should be separated into it's own individual codebases.
