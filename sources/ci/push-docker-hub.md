page_main_title: Push Docker image to Docker Hub
main_section: CI
sub_section: Pushing artifacts

#Pushing a Docker image to Docker Hub

You can push your image to Docker Hub in any section [of your yml](../platform/shippable-yml/). Typically, you would want to push your image at the end of the `ci` section, or in the `post_ci` or `push` sections.

##Setup

Before you start, you will need to connect your Docker Hub account with Shippable so we have the credentials to push your image on your behalf.

To add the Docker hub account, please follow steps [here](/platform/integration/docker-hub/#docker-hub-integration). Once you add an account integration, you can use it for all your projects without needing to add it again.

##Basic config

2. After completing the Setup step, add the following to the `shippable.yml` for your project. This snippet tells our service to
authenticate with Docker Hub using your credentials.

```
integrations:                               
  hub:
    - integrationName: myIntegration    #replace with your integration name   
      type: docker                        
```

3. Push to Docker hub in your `shippable.yml` file:

```
build:
  post_ci:
    - docker push docker-hub-org/image-name:image-tag
```

You can replace your docker-hub-org, image-name, and image-tag as required in the snippet above.

## Advanced config
### Limiting branches

By default, your integration is valid for all branches. If you want to only push your image for specific branch(es), you can do so with the `branches` keyword.

```
build:
  post_ci:
    - if [ "$BRANCH" == "master" ]; then docker push docker-hub-org/image-name:image-tag; fi

integrations:                               
  hub:
    - integrationName: myIntegration    #replace with your integration name   
      type: docker    
      branches:
        only:
          - master

```
In addition to the `only` tag which includes specific branches, you can also use the `except` tag to exclude specific branches.

### Pushing to different accounts based on branch

You can also choose to push your images to different Docker Hub accounts, depending on branch.

```
build:
  post_ci:
    - if [ "$BRANCH" == "master" ]; then docker push docker-hub-org-1/image-name:image-tag; fi
    - if [ "$BRANCH" == "dev" ]; then docker push docker-hub-org-2/image-name:image-tag; fi

integrations:                               
  hub:
    - integrationName: master-DockerHub    #replace with your integration name   
      type: docker    
      branches:
        only:
          - master

    - integrationName: dev-DockerHub    #replace with your integration name   
      type: docker    
      branches:
        only:
          - dev

```

###Pushing the CI container with all artifacts intact

If you are pushing your CI container to Docker Hub and you want all build artifacts preserved, you should commit the container before pushing it as shown below:

```
build:
  post_ci:
    #Commit the container only if you want all the artifacts from the CI step
    - docker commit $SHIPPABLE_CONTAINER_NAME docker-hub-org/image-name:image-tag
    - docker push docker-hub-org/image-name:image-tag

integrations:                               
  hub:
    - integrationName: myIntegration    #replace with your integration name   
      type: docker              
```

The environment variable `$SHIPPABLE_CONTAINER_NAME` contains the name of your CI container.

###Pushing Docker images with multiple tags

If you want to push the container image with multiple tags, you can just push twice as shown below:


```
build:
  post_ci:
    - docker push docker-hub-org/image-name:image-tag-1
    - docker push docker-hub-org/image-name:image-tag-2

integrations:                               
  hub:
    - integrationName: myIntegration    #replace with your integration name   
      type: docker

```
## Sample project

Here are some links to a working sample of this scenario. This is a simple Node.js application that runs some tests and then pushes
the image to Docker Hub.

**Source code:**  [devops-recipes/ci-push-docker-hub](https://github.com/devops-recipes/ci-push-docker-hub).

**Build link:** <a href="https://app.shippable.com/github/devops-recipes/ci-push-docker-hub/runs/1/1/console" target="_blank"> CI build on Shippable</a>

**Docker Hub image pushed:** [devopsrecipes/push-docker-hub](https://hub.docker.com/r/devopsrecipes/push-docker-hub/)

**Build status badge:** [![Run Status](https://api.shippable.com/projects/58f002c7c585000700aef8ca/badge?branch=master)](https://app.shippable.com/github/devops-recipes/ci-push-docker-hub)

## Improve this page

We really appreciate your help in improving our documentation. If you find any problems with this page, please do not hesitate to reach out at [support@shippable.com](mailto:support@shippable.com) or [open a support issue](https://www.github.com/Shippable/support/issues). You can also send us a pull request to the [docs repository](https://www.github.com/Shippable/docs).
