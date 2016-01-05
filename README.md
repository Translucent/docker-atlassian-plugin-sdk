# Atlassian Plugin SDK wrapped in a Docker container

This is an Docker image that has the Atlassian Plugin SDK, AMPS, installed and is extending the official Java image from the Docker Hub repositories. It has been made as an experiment to make development and collaboration on extending Atlassian products easier to work with by using Docker and all its glory.

## Quickstart

If you want to get up and running fast you can run the following which will start an Atlassian JIRA instance using the `atlas-run-standalone` command. After a short while the instance should be available at [http://docker-host:2990](http://docker-host:2990).

```
docker run -d -p 2990:2990 translucent/atlassian-plugin-sdk:latest atlas-run-standalone --product jira
```

Afterwards you could do your development using an externally hosted JIRA development instance and install new builds of your add-on by executing the following command provided that you also have AMPS installed on your local environment.

```
atlas-install-plugin --server docker-host
```

To see other suggestions on how to use the AMPS Docker image have a look [here](https://github.com/maj-translucent/docker-atlassian-plugin-templates).

## How do I implement this?

To see examples of the development workflow using this Docker image with both the `latest` and `onbuild` tags have a look in our
[examples repository](https://github.com/maj-translucent/docker-atlassian-plugin-templates) where we supply various workflow examples and experiments on how to utilize Docker to improve the development speed and workflow.

More information will be provided when the appropiate knowledge has been obtained.

[forced update]
