The twelve-factor app uses strict separation between the build, release, and run stages.

A codebase is transformed into a (non-development) deploy through three stages:

The build stage is a transform which converts a code repo into an executable bundle known as a build. Using a version of the code at a commit specified by the deployment process, the build stage fetches vendors dependencies and compiles binaries and assets.

The release stage takes the build produced by the build stage and combines it with the deploy’s current config. The resulting release contains both the build and the config and is ready for immediate execution in the execution environment.

The run stage (also known as “runtime”) runs the app in the execution environment, by launching some set of the app’s processes against a selected release.

For example, it's now impossible to make changes to the runtime. Instead, you make changes to the code in the build stage where you have total control. This reduces risk and ensures your team that everything is running well.

Here is the one of the example:

<img src="images\image-4.png" alt="build-release-run">