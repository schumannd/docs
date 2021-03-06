page_main_title: Node Cluster
main_section: Platform
sub_section: Integrations
page_title: Node cluster integration

# Node Cluster Integration

Available under the Integration Family: **deploy**

`Node Clster` Integration is used to connect Shippable DevOps Assembly Lines platform to a cluster of VMs and deploy apps to the entire cluster

You can create this from the integrations page. This is the information you would require to create this integration

* **Name** -- friendly name for the integration
* **Username** -- Username to login to Mesos master VM
* **Validity Period** -- Certificate validity in number of days

## Resources that use this Integration
Resources are the bulding blocks of assembly lines and some types of resource refer to Integrations by their name. The following Resources Types can created with `AWS` Integration 

* [cluster](/workflow/platform/resource/cluster)
* [integration](/workflow/platform/resource/integration)

## Default Environment Variables
When you create a Resource with this integration, and use it as an `IN` or `OUT` into a Job that can execute user defined scripts, a set of environment variables are configured by the platform that may be useful to set the context before user defined scripts execute as part of the Job. These are variables available when this Resource is used

`<NAME>` is the the friendly name of the Resource

| Environment variable						| Description      |
| ------			 							|----------------- |
| `<NAME>`\_INTEGRATION\_NAME				| Name supplied in the integration |
| `<NAME>`\_INTEGRATION\_NODES_0        | List of Nodes 0 to N supplied in the integration |
| `<NAME>`\_INTEGRATION\_PRIVATEKEY		| Private key used to access VMs |
| `<NAME>`\_INTEGRATION\_PUBLIKEY			| Public key used to access VMs |

## Shippable Utility Functions
To make it easy to GET and SET with these Environment Variables, the platform provides a bunch of utility functions so that you don't need to perform string concatenations etc. to work with this values.

How to use these utility functions are [documented here](/platform/tutorial/workflow/howto-use-shipctl)

## Further Reading
* [Quick Start to CI](/getting-started/ci-sample)
* [RunSh Job](/platform/workflow/job/runsh)
* [Jobs](/platform/workflow/job/overview)
* [Resources](/platform/workflow/resource/overview)
