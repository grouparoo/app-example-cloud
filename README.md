# Grouparoo `app-example-cloud`

_An example project for setting up automatic validation and deployment for Grouparoo on Grouparoo Cloud._

Goal: To create a scalable and flexible Grouparoo deployment that:

- Has no servers to directly manage
- Validates Grouparoo configuration on Pull Requests
- Automatically deploys Grouparoo configuration on pushes to `main`
- Is a [12-factor app](https://12factor.net/) with all configuration stored in the Environment

You can learn more about how this works by [reading the documentation](https://grouparoo.com/docs/cloud), or take a brief tour by watching the video below:

[![Grouparoo Cloud Video](https://img.youtube.com/vi/pI9Af4FJ3ws/0.jpg)](https://www.youtube.com/watch?v=pI9Af4FJ3ws)

## How We Got Here

> Some of the setup steps have already been done for you to create this app. Here's what we've taken care of:

1. Create a new Grouparoo project. Learn more @ https://www.grouparoo.com/docs/installation.

```
npm install -g grouparoo
grouparoo init .
```

2. Configure Grouparoo as needed through our Config UI. For this example, we are sending our users from Snowflake into Hubspot.

```
grouparoo config
```

3. Add a `.github/workflows/grouparoo-cloud.yml` GitHub Actions Workflow file to set up automatic config validation and deployment. An example workflow is available in your project's Integrations page in Grouparoo Cloud, but you can also take a look at the full example [in this repository](https://github.com/grouparoo/app-example-cloud/blob/main/.github/workflows/grouparoo-cloud.yml).

## Making configuration changes

Assuming you have node.js and the `grouparoo` cli installed:

1. `git clone https://github.com/grouparoo/app-example-cloud.git`
2. `cd app-example-cloud`
3. `npm install`
4. `cp .env.example .env`
5. Add your Hubspot and Snowflake credentials to your `.env` file
6. `grouparoo config`

## Deployment Steps

1. Sign up for Grouparoo Cloud at [https://www.grouparoo.com/trial](https://www.grouparoo.com/trial).
2. Once your instance is ready, go to your project's Integrations page on Grouparoo Cloud and set up the relevant GitHub secrets on your repository, as indicated by the instructions.
3. Go to your project's Secrets page on Grouparoo Cloud and set up any sensitive details you may need to specify to connect to your Sources and Destinations.
4. Create a Pull Request to start validating and deploying new configuration!

For more detailed steps, visit the docs at https://www.grouparoo.com/docs/cloud/repository-integration

---

Visit https://github.com/grouparoo/app-examples to see other Grouparoo Example Projects.
