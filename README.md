# continuous-build

This is the continuous build repository, with example configurations (and a basic 
one set up to run on CircleCI) to show how you can use repo2docker to build
a container that serves your notebook for others to use.

## Documentation

For complete documentation, please see 
[repo2docker](https://repo2docker.readthedocs.io/en/latest/deploy.html) 
on ReadTheDocs.

## Examples Provided

A circle configuration will be automatically detected in a hidden folder (`.circleci`)
that has a config.yml inside. In this repository, we have such a folder, and
this can be considered the base template for you to work from.

  - [.circleci](.circleci): 

We will be adding other example templates here as they are requested. For example,
it would be useful to have further testing of the container, or conversion with nbconvert.
These functions are not provided by default in the configuration above as they may not
be desired for all users. 

## Request an Example

If you want to get help, or request an example, please [let us know!](https://www.github.com/binder-examples/continuous-build/issues)
