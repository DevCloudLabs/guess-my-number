First, we’d need a gh-pages dev dependency, let’s add it by running:

npm install gh-pages --save-dev

Second, let’s add our website URL to the top-level declaration in the package.json file, for example, I’d have it like this:

"homepage": "https://iliailin.github.io/elo-foosball"

Third and last step before deploying we need to declare deployment scripts in the scripts section of the package.json file:

"predeploy": "npm run build",
"deploy": "gh-pages -d build",

As of this moment, we are done with configuring, let’s run

npm run deploy

This command will do the following:

    run pre-deploy script building our application source code
    create a git branch with the name gh-pages if it didn’t exist before (like from previous executions of this command)
    push compiled code to this branch and serve it to the webpage under the URL we specified in the second step. Settings of the GitHub repository will change correspondingly, like serving from the gh-pages branch.
    The webpage will be live in a couple min

Note: when executing npm run deploy you will most probably be prompted with credentials to continue, they tend to appear several times and may not work in all terminals by default.