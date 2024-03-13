# githubdeployments-node-example

An example plugin repository with a workflow script that installs Node dependencies.

The [workflow](.github/workflows/wpcom.yml) does the following:

- Checkout the repository
- Runs `npm install` which is the default behaviour of the [Node Action](https://github.com/actions/setup-node)
- Stores NPM packages in a cache named `npm`
- Runs `npm css` which minifies our css and copies the output to `/css`
- Create a build artifact with name `wpcom` which is required for WordPress.com's GitHub Deployment feature, while also excluding files from the deployment, like `package.json`, `style.css`, and `README.md`
