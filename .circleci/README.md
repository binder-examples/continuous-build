# CircleCI 2.0 Workflow Templates

This folder contains template files for CircleCI workflow configurations. You should
choose the one that you want to use, and name it to be the file `.circleci/config.yml`
in your repository. Each is described below, along with a description of environment
variables that you can define in the CircleCI project settings to customize the build.

## Where do I define the variables?
For each set of variables, some you can define in the config.yml, in the `environment`
section for a workflow step, for example, here is setting the variable `TIMEZONE`
to be defined as `/usr/share/zoneinfo/America/Los_Angeles` available during the
"setup" step:

```bash
  setup:
    environment:
      - TIMEZONE: "/usr/share/zoneinfo/America/Los_Angeles"
```

or you can define variables in the [CircleCI project settings](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project). 
The latter is recommended for sensitive information. 

For all configuration descriptions below, **all variables** from both tables 
can be set in just the CircleCI project settings, if desired.

# Templates

## config.yml

This is a base, or default configuration to build.

**Variables that must be set in CircleCI Project Settings**

|Variable|Description|Required|Default|
|---|---|---|---|
|`DOCKER_USER`|Docker username to deploy to Docker Hub. The build will not deploy without it.|no|unset|
|`DOCKER_PASS`|Docker password to deploy to Docker Hub. The build will not deploy without it.|no|unset|

**Variables that can be set in config.yml**
 
|Variable|Description|Required|Default|
|---|---|---|---|
|`CONTAINER_NAME`|The name of the Docker Hub container to deploy|no|`<ORG>/<REPO>`|
|`DOCKER_TAG`|A custom tag for the deployed image.|no|the first 10 characters of the commit.|


## config.singularity

This configuration is equivalent to the default config.yml, with the additional change in permissions of the
repo2docker folder to allow for the user to write given export into a Singularity container. If you want your
container notebooks to be usable on a shared resource, you should choose this configuration.

**Variables that must be set in CircleCI Project Settings**

|Variable|Description|Required|Default|
|---|---|---|---|
|`DOCKER_USER`|Docker username to deploy to Docker Hub. The build will not deploy without it.|no|unset|
|`DOCKER_PASS`|Docker password to deploy to Docker Hub. The build will not deploy without it.|no|unset|

**Variables that can be set in config.yml**

|Variable|Description|Required|Default|
|---|---|---|---|
|`CONTAINER_NAME`|The name of the Docker Hub container to deploy|no|`<ORG>/<REPO>`|
|`DOCKER_TAG`|A custom tag for the deployed image.|no|the first 10 characters of the commit.|
|`NOTEBOOK_PERMISSION`|The permission to (recursively) give the notebook, to allow write.|no|777|
|`NOTEBOOK_USERNAME`|The username (to derive the home directory) to build the notebook and virtual environment. (e.g., `/home/joyvan`|no|`joyvan`|

