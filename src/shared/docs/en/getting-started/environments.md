## Overview

Each of your Begin app's three hosted environments (`testing`, `staging`, and `production`) has its own set of independently configurable environment variables.

The name of each environment is available by default as `NODE_ENV`.

Configured variables are available to all processes within each environment at runtime.


## Adding variables

To add your environment variables, open `Environments` in the left nav in Begin.

Under the environment you want to add a variable to (i.e. `staging`), add your key and value, and click `Add`.

This variable is now available to all your Functions in `staging` – no deploy necessary!

![Begin activity](/_static/screens/shared/begin-env-console.jpg)

> Note: keys can only contain upper case alphanumeric characters and underscores (`[A-Z0-9_]`), and must start with a letter. Values are limited to 255 characters.


## Editing variables

To modify an existing environment variable, overwrite it with a new variable with the key you want to overwrite.

To delete a variable, simply click the red delete icon.

## Using Variables While Developing

When working in your development environment, you may need to provide different environment variables. Begin uses [Architect](https://arc.codes/) to run your functions, and the same applies for local development. 

*You can see the environment variables documentation for Architect [here](https://arc.codes/reference/cli/env#the-arc-env-file).*

**To add an environment variable:** 

- add a `.arc-env` file to the root of your project. 
- also include in your `.gitignore` file. 

The `.arc-env` file is automatically read by `arc sandbox` and populates `process.env`

For your development environment, you should use the `@testing` environment. Your `.arc-env` file may look like this:

```bash
# example .arc-env

@testing 
SOME_VAR some-value
```
