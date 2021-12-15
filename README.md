# Grouparoo `app-example-cloud`

_An example project for setting up automatic validation and deployment for Grouparoo on Grouparoo Cloud._

Goal: To create a scalable and flexible Grouparoo deployment that:

- Has no servers to directly manage
- Validates Grouparoo configuration on Pull Requests
- Automatically deploys Grouparoo configuration on pushes to `main`
- Is a [12-factor app](https://12factor.net/) with all configuration stored in the Environment

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

3. Add a `grouparoo-cloud.yml` GitHub Actions Workflow file to set up automatic config validation and deployment. An example workflow is available in your project's Integrations page in Grouparoo Cloud, but you can also take a look at the full example [in this repository](https://github.com/grouparoo/app-example-cloud/blob/main/.github/workflows/grouparoo-cloud.yml).


## Making configuration changes

Assuming you have node.js and the `grouparoo` cli installed:

1. `git clone https://github.com/grouparoo/app-example-cloud.git`
2. `cd app-example-cloud`
3. `npm install`
4. `cp .env.example .env`
5. `grouparoo config`

## Deployment Steps

1. Sign up for Grouparoo Cloud at [https://www.grouparoo.com/trial](https://www.grouparoo.com/trial).
2. Once your instance is ready, go to your project's Integrations page on Grouparoo Cloud and set up the relevant GitHub secrets on your repository, as indicated by the instructions.

![image](https://user-images.githubusercontent.com/4368928/146205580-cc01a0d4-359d-43ef-af64-79b95129d3c9.png)

3. Go to your project's Secrets page on Grouparoo Cloud and set up any sensitive details you may need to specify to connect to your sources and destinations.

![image](https://user-images.githubusercontent.com/4368928/146205316-32ea4ba4-8607-45cb-a6dc-b307f67aa95d.png)

4. Create a Pull Request to start validating and deploying new configuration!

---

Visit https://github.com/grouparoo/app-examples to see other Grouparoo Example Projects.
