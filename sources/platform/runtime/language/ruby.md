page_main_title: Ruby Language Overview
main_section: Platform
sub_section: Runtime
sub_sub_section: Languages
page_title: CI/CD for Ruby Applications

# Ruby
This section explain how Shippable DevOps Assembly Lines Platform behaves when you set `language: ruby` in your [shippable.yml](/platform/tutorial/workflow/shippable-yml) for a [runCI Job](/platform/workflow/job/runci), 

```
language: ruby
rvm:
  - 2.4.1
```

We use Ubuntu 14.0 version of the language image by default, the latest that was available when your project was enabled. You can override this by using `pre_ci_boot` section or even [build your own image](/ci/custom-docker-image) from scratch.

<a name="versions"></a>
## Versions
This table helps you choose the right tag for the language version that your app needs and it is set in the YML. 

The tags denote which `edition` of the [Runtime AMI](/platform/tutorial/runtime/ami-overview) has that particular version installed. Any tag can be used on any , but each edition of the AMI has that edition cached which will improve your build speed

| Version  |  Tags    
|----------|---------
|2.4.1 |   v5.7.3    
|2.3.4 |   v5.7.3    
|2.3.3 |  v5.6.1 and earlier 
|2.3.2 |  v5.6.1 and earlier 
|2.3.1 |  v5.6.1 and earlier 
|2.3.0 |  v5.6.1 and earlier 
|2.2.7 |   v5.7.3    
|2.2.5 |  v5.6.1 and earlier 
|2.2.1 |  v5.6.1 and earlier 
|2.1.5 |  v5.6.1 and earlier 
|2.0.0 |  v5.6.1 and earlier 
|1.9.3 |  v5.6.1 and earlier 
|1.8.7 |  v5.6.1 and earlier 
|jruby 9.1.12        |   v5.7.3    
|jruby 9.1.5         |  v5.6.1 and earlier 
|jruby 9.1.2         |  v5.6.1 and earlier 
|jruby 9.0.0         |  v5.7.3 and earlier 
|jruby 1.7.27        |   v5.7.3    
|jruby 1.7.19        |  v5.6.1 and earlier 
|ree 1.8.7           |  v5.6.1 and earlier

You can use more than 1 of these to test your app against multiple version using [matrix build](/ci/matrix-builds)

## Default Behavior

```
build:
  ci: <is not set>
```

If you do not set the `ci` section of the YML, then we will inject this section to your YML definition at runtime

```
build:
  ci:
    - bundle install --gemfile=$SHIPPABLE_GEMFILE $SHIPPABLE_BUNDLER_ARGS
```

## Shippable provided Runtime images
Each of the language image is built from the respective base OS version of the image. Since we install all the all the packages, CLIs & services installed on the base image, these language images get this automatically. For more information visit the respective base image page.

### Ubuntu 16.04

**Built from** [drydock/u16all](/platform/runtime/os/ubuntu16)

|Image| Release Date |Available in AMI | 
|----------|------------|-----|
drydock/u16ruball:v5.7.3  | Jul 2017 - Latest Version | [v5.7.3](/platform/tutorial/runtime/ami-v573)
drydock/u16ruball:v5.6.1  | Jun 2017  | [v5.6.1](/platform/tutorial/runtime/ami-v561)
drydock/u16ruball:v5.5.1  | May 2017  | [v5.5.1](/platform/tutorial/runtime/ami-v551)
drydock/u16ruball:v5.4.1  | Apr 2017  | [v5.4.1](/platform/tutorial/runtime/ami-v541)
drydock/u16ruball:v5.3.2  | Mar 2017  | [v5.3.2](/platform/tutorial/runtime/ami-v532)

### Ubuntu 14.04

**Built from** [drydock/u14all](/platform/runtime/os/ubuntu14)

|Image| Release Date |Available in AMI | 
|----------|------------|-----|
drydock/u14ruball:v5.7.3  | Jul 2017 - Latest Version | [v5.7.3](/platform/tutorial/runtime/ami-v573)
drydock/u14ruball:v5.6.1  | Jun 2017  | [v5.6.1](/platform/tutorial/runtime/ami-v561)
drydock/u14ruball:v5.5.1  | May 2017  | [v5.5.1](/platform/tutorial/runtime/ami-v551)
drydock/u14ruball:v5.4.1  | Apr 2017  | [v5.4.1](/platform/tutorial/runtime/ami-v541)
drydock/u14ruball:v5.3.2  | Mar 2017  | [v5.3.2](/platform/tutorial/runtime/ami-v532)

## Further Reading
* [Everything about Shippable AMIs](/platform/tutorial/runtime/ami-overview)
* [Quick Start to CI](/getting-started/ci-sample)
* [Continuous Integration of a Ruby application](/ci/ruby-continuous-integration)
* [Checking which AMI is your Project using](/platform/visibility/subscription/nodes)