Store config in the environment

An app’s config is everything that is likely to vary between deploys (staging, production, developer environments, etc). This includes:

    Resource handles to the database, Memcached, and other backing services

    Credentials to external services such as Amazon S3 or Twitter

    Per-deploy values such as the canonical hostname for the deploy

The twelve-factor app stores config in environment variables (often shortened to env vars or env). Env vars are easy to change between deploys without changing any code; unlike config files, there is little chance of them being checked into the code repo accidentally; and unlike custom config files, or other config mechanisms such as Java System Properties, they are a language- and OS-agnostic standard.

Configuration that varies between deployments should be stored in the environment.

For example, you do not want sensitive information like database credentials or API keys to be committed into the repository to prevent security leaks.

Here the example of having config on .env file.

<img src="images\image-3.png" alt="config">