Clone sample nodejs repo to /opt/ directory
Repo URL: https://github.com/contentful/the-example-app.nodejs

````bash
thor@host01 ~$ cd /opt/

thor@host01 /opt$ sudo git clone  https://github.com/contentful/the-example-app.nodejs
Cloning into 'the-example-app.nodejs'...
remote: Enumerating objects: 2935, done.
remote: Counting objects: 100% (21/21), done.
remote: Compressing objects: 100% (21/21), done.
remote: Total 2935 (delta 12), reused 2 (delta 0), pack-reused 2914
Receiving objects: 100% (2935/2935), 6.81 MiB | 30.05 MiB/s, done.
Resolving deltas: 100% (1770/1770), done.
````

We have installed node for you . Install dependencies with npm and run app.js in /opt/the-example-app.nodejs/ directory with node and observe output if any.

````bash
thor@host01 /opt$ cd the-example-app.nodejs/
thor@host01 /opt/the-example-app.nodejs$ sudo npm install; node app.js
````

Run app in start:dev mode and observe the webpage in the Browser.

````bash
thor@host01 /opt/the-example-app.nodejs$ npm run start:dev

    > example-contentful-theExampleApp-js@0.0.0 start:dev
    > node ./bin/www

    Listening on http://localhost:3000
````

Now install the latest version of pm2 by using npm with -g flag.

````bash
thor@host01 /opt/the-example-app.nodejs$ sudo npm install pm2@latest -g

    added 138 packages in 4s

    13 packages are looking for funding
    run `npm fund` for details

thor@host01 /opt/the-example-app.nodejs$ sudo npm dist-tag pm2
    0.10.0-beta10: 0.10.0-beta10
    0.10.0-beta11: 0.10.0-beta11
````

Run app with pm2 and observe the output in console

````bash
thor@host01 /opt/the-example-app.nodejs$ pm2 start app.js
````

Run app with pm2 but with 4 forks. observe the output in console
pm2 process already running in previos step so stop that process and run with new options

````bash
thor@host01 /opt/the-example-app.nodejs$ pm2 delete app.js
[PM2] Applying action deleteProcessId on app [app.js](ids: [ 0 ])
[PM2] [app](0) ✓
┌────┬────────────────────┬──────────┬──────┬───────────┬──────────┬──────────┐
│ id │ name               │ mode     │ ↺    │ status    │ cpu      │ memory   │
└────┴────────────────────┴──────────┴──────┴───────────┴──────────┴──────────┘

thor@host01 /opt/the-example-app.nodejs$ pm2 start app.js -i 4
[PM2] Starting /opt/the-example-app.nodejs/app.js in cluster_mode (4 instances)
[PM2] Done.
┌────┬────────────────────┬──────────┬──────┬───────────┬──────────┬──────────┐
│ id │ name               │ mode     │ ↺    │ status    │ cpu      │ memory   │
├────┼────────────────────┼──────────┼──────┼───────────┼──────────┼──────────┤
│ 0  │ app                │ cluster  │ 0    │ online    │ 0%       │ 54.7mb   │
│ 1  │ app                │ cluster  │ 0    │ online    │ 0%       │ 52.8mb   │
│ 2  │ app                │ cluster  │ 0    │ online    │ 0%       │ 49.0mb   │
│ 3  │ app                │ cluster  │ 0    │ online    │ 0%       │ 46.3mb   │
└────┴────────────────────┴──────────┴──────┴───────────┴──────────┴──────────┘
````