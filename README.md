# githubdeployments-node-example

An example plugin repository with a workflow script that installs Node dependencies.

The [workflow](.github/workflows/wpcom.yml) does the following:

- Checkout the repository
- Instals Node with the [Node Action](https://github.com/actions/setup-node)
- Runs `npm install` to install dependencies in `package.json`
- Stores NPM packages in a cache named `npm`
- Runs `npm run minify-css` which minifies the css and copies the output to `/css`
- Creates a build artifact with name `wpcom` which is required for WordPress.com's GitHub Deployment feature, while also excluding files from the deployment, like `package.json`, `style.css`, and `README.md`
