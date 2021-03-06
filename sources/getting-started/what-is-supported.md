page_main_title: What does Shippable support?
main_section: Getting started
sub_section: Overview

# What is supported?

[Shippable DevOps Assembly Line Platform](platform/overview) supports most of the popular tools and technology used today to build, test, deploy and operate applications/services/micro-services

Here are some of the major things we support out of the box. With that being said, the Platform is built with Docker in mind. Hence, anything that can be installed inside of a Docker image is supported by the platform

## Node Types
To run you DevOps activities, you need a Node (virtual machine). Shippable support 2 types of Nodes

* [Dedicated Dynamic Nodes](/platform/runtime/overview#nodes) -- these are managed and dynamically provisioned by Shippable Platform. There is no need to worry about managing build infrastructure. There are multiple sizes that you can use depending on your need
	* 2 core, 3.75GB RAM (default) -- this is equivalent of AWS c4.large instance type
	* 4 core, 7.5GB RAM -- this is equivalent of AWS c4.xlarge instance type
	* 8 core, 15GB RAM -- this is equivalent of AWS c4.2xlarge instance type
	
* [Dedicated Custom Nodes](/platform/runtime/overview#nodes) -- these are Nodes that you manage it yourself and hook it to Shippable Assembly Lines to run your DevOps activities. The biggest reason for doing this is that all your code never leaves your infrastructure. Another reason to do this would be that your jobs require access to internal resources that you dont want to be accessible from the internet. You could run these Nodes anywhere you like.

## Operating System
The platform is designed to work on any Linux distro. We natively support the following 

* [Ubuntu 14.04 LTS](/platform/runtime/os/ubuntu14)
* [Ubuntu 16.04 LTS](/platform/runtime/os/ubuntu16)

As mentioned before, we are a Docker based platform. Hence any custom image based on a Linux distro can be used in Job Runtime. For more details visit the [Operating Systems page](/platform/runtime/os)

## Language
For both the OS versions, we maintain [language](/platform/runtime/language/overview) specific images that are updated every month so that the latest and greatest versions are always available.
We support the following languages

* [Clojure](/platform/runtime/language/clojure)
* [GO](/platform/runtime/language/go)
* [Java](/platform/runtime/language/java)
* [Node JS](/platform/runtime/language/nodejs)
* [PHP](/platform/runtime/language/php)
* [Python](/platform/runtime/language/python)
* [Ruby](/platform/runtime/language/ruby)
* [Scala](/platform/runtime/language/scala)

## Services
To make your builds even faster, we also pre-install a bunch of [Services](/platform/runtime/language/overview) that your application may need. These are also updated on a monthly cadence.

Following are the service that are pre-installed

* [Cassandra](/platform/runtime/service/cassandra)
* [CouchDB](/platform/runtime/service/couchdb)
* [ElasticSearch](/platform/runtime/service/elasticsearch)
* [Memcached](/platform/runtime/service/memcached)
* [MongoDB](/platform/runtime/service/mongodb)
* [MySQL](/platform/runtime/service/mongodb)
* [Neo4j](/platform/runtime/service/neo4j)
* [Postgres](/platform/runtime/service/postgres)
* [RabbitMQ](/platform/runtime/service/rabbitmq)
* [Redis](/platform/runtime/service/redis)
* [RethidDB](/platform/runtime/service/rethinkdb)
* [Riak](/platform/runtime/service/riak)
* [Selenium](/platform/runtime/service/selenium)
* [SqlLite](/platform/runtime/service/sqllite)

## Testing Frameworks
Our [Images](/platform/runtime/overview) also come pre-installed with all the tooling necessary to runs tests based on a plethora of frameworks. Some of the popular ones are

* JUnit
* XUnit
* RSpec
* Nosetest
* Chai/Mocha
* ...and more

## Command Line Interfaces (CLI)
Majority of the apps today run on cloud. Each cloud provider has a native CLI and we want to avoid you having to install and configure them. In addition we also pre-install some popular DevOps tools also. The goals is to try and prep the build environment as close to your desired state so that you can spend less time prepping and more time developing applications.

Here is a list of CLIs we have available as part of Job Runtime

* [Ansible](/platform/runtime/cli/ansible)
* [AWS](/platform/runtime/cli/aws)
* [AWS Elastic Beanstalk](/platform/runtime/cli/awseb)
* [Azure](/platform/runtime/cli/azure)
* [Docker](/platform/runtime/cli/docker)
* [GKE](/platform/runtime/cli/gke)
* [JFrog](/platform/runtime/cli/jfrog)
* [Packer](/platform/runtime/cli/packer)
* [Terraform](/platform/runtime/cli/terraform)
* [Kubectl](/platform/runtime/cli/kubectl)

## 3rd Party Integrations
In addition we support a multitude of integrations into external providers. This makes it easy to plug in any of your existing tooling seamlessly into Shippable Assembly Line Platform

### Source Control Management

-  [GitHub](/platform/integration/github)
-  [GitHub Enterprise](/platform/integration/github-enterprise)
-  [Bitbucket](/platform/integration/bitbucket)
-  [Bitbucket Server](/platform/integration/bitbucket)
-  [GitLab](/platform/integration/gitlab)

### Cloud Providers

-  [Amazon Web Services](/platform/integration/aws)
-  [Google Cloud](/platform/integration/gce)
-  [Microsoft Azure](/platform/integration/azure)
-  [Digital Ocean](/platform/integration/do)

### Container Orchestration Systems

- [AWS Elastic Beanstalk](/platform/runtime/cli/awseb)
- [AWS Elastic Container Service](/platform/integration/aws)
- [Mesos DC/OS](/platform/integration/azure-dcos)
- [Kubernetes](/platform/integration/kubernetes)
- [Google Container Engine](/platform/integration/gce)

- [Azure Container Service](/platform/integration/azure)
- [Joyent Triton](/platform/integration/tripub)
- [Docker Datacenter](/platform/integration/docker-datacenter)
- [Docker Cloud](/platform/integration/docker-cloud)

### Artifact Repositories

- [Docker Hub](/platform/integration/docker-hub)
- [Docker Trusted Registry](/platform/integration/docker-trusted-registry)
- [AWS Elastic Container Registry](/platform/integration/aws-ecr)
- [Google Container Registry](/platform/integration/gcr)
- [Quay](/platform/integration/quay)
- [JFrog Artifactory](/platform/integration/jfrog-artifactory)
- [AWS S3](/platform/integration/aws)

### Messaging Providers

- [Slack](/platform/integration/slack)
- [Hipchat](/platform/integration/hipchat)
- [IRC](/platform/integration/irc)
- [Email](/platform/integration/email)
- [Custom Webhooks](/platform/integration/event-trigger)

### PaaS Providers

- [AWS Opsworks](/platform/integration/aws)
- [AWS Elastic Beanstalk](/platform/integration/aws)
- [Heroku](/platform/integration/key-value)

### IaaS Providers

-  [AWS EC2](/platform/integration/aws)
-  [Google Cloud](/platform/integration/gce)
-  [Microsoft Azure](/platform/integration/azure)
-  [Digital Ocean](/platform/integration/do)

### DevOps Tools

- [Ansible](/platform/runtime/cli/ansible)
- Chef
- Puppet
- Saltstack
- [AWS Cloud Formations](/platform/runtime/cli/aws)
- [Terraform](/platform/runtime/cli/terraform)
- [Packer](/platform/runtime/cli/packer)

### Deployment Tools

- [AWS Codedeploy](/platform/runtime/cli/aws)
- Capistrano

## Further Reading
* [Platform Overview](platform/overview)
* [Quick Start to CI](getting-started/ci-sample)
* [Quick Start to CD](getting-started/cd-sample)
