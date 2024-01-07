## Requirements

- Node 18 or higher

## Let's get started

Open the [Fern Docs Starter](https://github.com/fern-api/docs-starter) GitHub repository, then follow the steps below to generate your documentation. 

### Step 1: Use this template

1. From the Fern Docs Starter GitHub repository, click the `Use this template` button. You must be logged into GitHub.
2. Create a new repository. Name it anything you like; `docs` is a common naming choice.

### Step 2: Clone and open in your preferred code ditor

Clone your newly created repository and open it in your favorite code editor.

The files and folders discussed in the following steps will be inside a `fern` folder in your repository. 

Any non-global CLI commands given below must be run from within your repository.

### Step 3: Customize organization name

In the `fern.config.json` file, replace the placeholder organization name with your actual organization name. For example:

```json
{
    "organization": "YourOrganization",
    "version": "0.15.18"
}
```

In the `docs.yml` file, update the docs URL to match your organization's naming convention. For example:

```yml
instances:
  - url: your-organization.docs.buildwithfern.com
```

### Step 4: Install the Fern CLI

Install the Fern CLI globally by running:

```bash
npm install -g fern-api
```

### Step 5 (Optional): Use an OpenAPI Specification

If you will be using [Fern Definitions](https://docs.buildwithfern.com/api-definition/fern-definition/overview) to describe your API, skip to [Step 6](#step-6-generate-your-documentation).

If you will be using an [OpenAPI Specification](https://docs.buildwithfern.com/api-definition/openapi/extensions), follow these steps:
1. Delete the `definition` folder, then run:

```bash
fern init --openapi URL_OR_LOCAL_PATH_TO_OPENAPI_SPEC
```

Examples:
```fern init --openapi https://petstore3.swagger.io/api/v3/openapi.json```
```fern init --openapi ../apis/openapi.yml```
You can use a URL to an OAS (OpenAPI Specification) file, or you can use a local path. The file must be formatted as JSON or YAML.

You should then see a `openapi` folder created inside your `fern` folder. This new folder will contain the OAS file you specified, in YAML format.

### Step 6: Generate your documentation

From within your cloned repository, generate your documentation with the following command:

```bash
fern generate --docs
```

You will be prompted to log in and connect your GitHub account.

Once the documentation is generated, you will receive a URL where your documentation is published. For example:

```shell
┌─
│ ✓  your-organization.docs.buildwithfern.com
└─
```

### Step 7: Customize Your Documentation

To update your API definitions:
- For Fern Definitions, update the files in the `definitions` folder.
- For OpenAPI definitions, update the file in the `openapi` folder. 

Next, modify the markdown pages located in the `docs/pages` folder.
Further tailor your documentation to match your brand by adjusting settings in the `docs.yml` file.

To re-publish your documentation with changes, run `fern generate --docs` again.

Fern has a built-in component library for you to use. [Explore the components.](https://docs.buildwithfern.com/generate-docs/component-library/)

### Step 8: Set up a custom domain

If you wish to use a custom domain like `docs.your-organization.com` or a subdirectory like `your-organization.com/docs`, you can subscribe to the [Starter plan](https://buildwithfern.com/pricing). Once subscribed, update `docs.yml` with the custom domain configuration:

``` yaml
 - url: your-organization.docs.buildwithfern.com
   custom-domain: docs.your-organization.com
```

### Step 9: Explore advanced features

For advanced documentation features and options, view the [Fern Docs](https://docs.buildwithfern.com/).
