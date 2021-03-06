page_main_title: Cassandra Service Overview
main_section: Platform
sub_section: Job Runtime
sub_sub_section: Services
page_title: CI/CD with Cassandra Applications

# Cassandra
This section explain how Shippable DevOps Assembly Lines Platform behaves when you set `services:` tag in your [shippable.yml](/platform/tutorial/workflow/shippable-yml) for a [runCI Job](/platform/workflow/job/runci)

All language images and all Operating Systems support this service

```
services:
  - cassandra
```

## Supported Versions
This table helps you choose the right tag based on the version of the service you might want to use

The tags denote which `edition` of the [Runtime AMI](/platform/tutorial/runtime/ami-overview) has that particular version installed. Any tag can be used on any , but each edition of the AMI has that edition cached which will improve your build speed

| Version  |  Tags    
|----------|---------
|1.6  | v5.7.3, v5.8.2

## Supported Languages
Since all [Language](/platform/runtime/language/overview) images are built from the the `all` versions of the OS as above, this service is also available if you use language specific images. Shippable platform automatically picks the latest language image based on your [CI YML settings](ci/set-language/), but if you need finer grain control, you can use the image tag sections of the YML.

* [Clojure](/platform/runtime/language/clojure)
* [GO](/platform/runtime/language/go)
* [Java](/platform/runtime/language/java)
* [Node JS](/platform/runtime/language/nodejs)
* [PHP](/platform/runtime/language/php)
* [Python](/platform/runtime/language/python)
* [Ruby](/platform/runtime/language/ruby)
* [Scala](/platform/runtime/language/scala)

## Supported OS Versions
This service is installed on to the base OS image along with other services. The following are tags and release dates of the base OS Image

### Ubuntu 16.04

|Image| Release Date |Available in AMI | 
|----------|------------|-----|
[drydock/u16all:v5.8.2](/platform/runtime/os/ubuntu16#v582)  | Aug 2017 - Latest | [v5.8.2](/platform/tutorial/runtime/ami-v582)
[drydock/u16all:v5.7.3](/platform/runtime/os/ubuntu16#v573)  | Jul 2017 | [v5.7.3](/platform/tutorial/runtime/ami-v573)

### Ubuntu 14.04

|Image| Release Date |Available in AMI | 
|----------|------------|-----|
[drydock/u14all:v5.8.2](/platform/runtime/os/ubuntu14#v582)  | Aug 2017 - Latest | [v5.8.2](/platform/tutorial/runtime/ami-v582)
[drydock/u14all:v5.7.3](/platform/runtime/os/ubuntu14#v573)  | Jul 2017 | [v5.7.3](/platform/tutorial/runtime/ami-v573)

## Further Reading
* [Everything about Shippable AMIs](/platform/tutorial/runtime/ami-overview)
* [Quick Start to CI](/getting-started/ci-sample)
