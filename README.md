# continuous-build

This is the continuous build repository, with example configurations (and a basic 
one set up to run on CircleCI) to show how you can use repo2docker to build
a container that serves your notebook for others to use.

## Documentation

You will generally want to copy the `.circleci` folder and its contents to your own folder
with some corresponding notebook and requirements file. For complete documentation, please see 
[repo2docker](https://repo2docker.readthedocs.io/en/latest/deploy.html) 
on ReadTheDocs.

## Examples Provided

Included in this example are:

 - [.circleci](.circleci): a hidden folder that contains the default configuration to build->deploy.
 - [example.ipynb](example.ipynb): an example ipython notebook that will be built in continuous integration
 - [requirements.txt](requirements.txt) an example requirements.txt file for the example notebook.

The circle configuration will be automatically detected in a hidden folder ([.circleci](.circleci))
that has a config.yml inside. In this repository, we have such a folder, and
this can be considered the base template for you to work from.

## Request an Example
We will be adding other example templates here as they are requested. For example,
it would be useful to have further testing of the container, or conversion with nbconvert.
These functions are not provided by default in the configuration above as they may not
be desired for all users. 

If you want to get help, or request an example, please [let us know!](https://www.github.com/binder-examples/continuous-build/issues)
