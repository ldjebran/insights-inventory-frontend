[![Build Status](https://jenkins-insights-jenkins.1b13.insights.openshiftapps.com/buildStatus/icon?job=insights-inventory-frontend/insights-inventory-frontend-ci)](https://jenkins-insights-jenkins.1b13.insights.openshiftapps.com/job/insights-inventory-frontend/job/insights-inventory-frontend-ci/)

# Insights Inventory Frontend

This is the frontend application for [Insights Inventory](https://github.com/RedHatInsights/insights-inventory). It is based on the [insights-frontend-starter-app](git@github.com:RedHatInsights/insights-frontend-starter-app.git).

## Getting Started
There is a [comprehensive quick start guide in the Storybook Documentation](https://github.com/RedHatInsights/insights-frontend-storybook/blob/master/src/docs/welcome/quickStart/DOC.md) to setting up an Insights environment complete with:
- A frontend application
- [Insights Chroming](https://github.com/RedHatInsights/insights-chrome)
- [Insights Proxy]

Note: You will need to set up the Insights environment if you want to develop the inventory app due to the consumption of the chroming service as well as setting up your global/app navigation through the API.

### Insights Proxy
[Insights Proxy](https://github.com/RedHatInsights/insights-proxy) is required to run the inventory frontend application. **Note that a inventory-specific proxy configuration is required for now for the frontend application to be able to talk to the Inventory API POC**. To run the proxy with inventory-specific configuration run:
```
SPANDX_CONFIG="$(pwd)/insights-inventory-frontend/config/spandx.config.js" bash insights-proxy/scripts/run.sh
```

### Running the app
1. ```npm install```

2. ```npm run start```
    - starts webpack bundler and serves the files with webpack dev server

### Running the app without insights-proxy

You don't have to run insights proxy to serve your application, you can use built in `webpack-proxy` by running
```
npm run start:proxy
```

### Running in beta environment

If you want to run inventory app in beta environment accessible on `/beta/insights/inventory` you can do that by add `BETA=true` before each start command

```
BETA=true npm start
```

or

```
BETA=true npm run start:proxy
```

or building for beta environment
```
BETA=true npm run build
```

### Testing
There is an npm script that runs the build, JS and CSS linters and unit tests. The script can be invoked by
`npm run verify`
