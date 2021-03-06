page_main_title: Working with Jobs
main_section: Platform
sub_section: Tutorials
sub_sub_section: Workflow
page_title: DevOps Assembly Line Jobs
page_description: How to add, delete and update jobs
page_keywords: Deploy multi containers, microservices, Continuous Integration, Continuous Deployment, CI/CD, testing, automation, pipelines, docker, lxc


# Working with Jobs
Shippable DevOps Platform leverages a declarative syntax for CRUD operations on Jobs. A YML `shippable.jobs.yml` config file is used to define them. It is added to your the root of your source code repo just like any other piece of code and the platform recognizes the changes you make to it through webhooks and sync the definitions.

<a name="adding"></a>
## Adding Jobs
Jobs are defined in a configuration file `shippable.jobs.yml` and this file is added to the root of a source control repository. All user permissions that users have on the repo is carried over to the objects defined in the YML. For example, if user 1 has read access he/she will only have read access to Jobs defined in the repo.

Once the Jobs are defined and added to the repo, you will have to connect it to SPOG by creating a `syncRepo` using the UI. Detailed step by step instructions are [here ](/platform/workflow/resource/syncrepo)

After adding a `syncRepo`, our DevOps Assembly Lines are watching for changes (Job adds, edits or deleted) through source control webhooks. YML changes are automatically synced and they are reflected in the SPOG immediately

<a name="migrate"></a>
## Migrating a Job from one YML to another
There are some situations where you might need to reorganize where your Jobs are defined. If you delete and recreate, you will lose all the historical versions. If history is important, migration might be a better alternative

Here are the steps to migrate -

Here are the steps to migrate -

1. Goto the SPOG page and pause the rSync job for the source repository from where you want to migrate resources, jobs or triggers. Steps for pausing the rSync jobs can be found [here](/platform//tutorial/workflow/howto-crud-job#pausing-jobs).

2. Add the jobs you want to migrate to the destination repository's yml files.

3. Run the rSync job of the destination repository. Once the rSync job completes, migration will be complete. Your SPOG will however not change as no dependency has changed. Therefore, to verify this you can check the logs of the rSync job.
<img src="/images/pipelines/migrationConsoleLog.png" alt="See the version list of your resource from the SPOG view" style="width:800px;vertical-align: middle;display: block;margin-left: auto;margin-right: auto;"/>

4. From the source repository, delete all the migrated jobs. This will automatically trigger the rSync job and it should succeed.
<img src="/images/pipelines/resumeJob.png" alt="See the version list of your resource from the SPOG view" style="width:800px;vertical-align: middle;display: block;margin-left: auto;margin-right: auto;"/>

5. Now, your jobs are migrated to the destination repository. You can add, remove or update them there.

**NOTE:** While migrating a job you should copy it exactly as it is in the source repository. You can add or remove dependencies only once the job is successfully migrated to destination repository.


<a name="pause"></a>
## Pausing jobs

You can pause any jobs in your pipeline by right-clicking on the job, and clicking **Pause Jobs**. Paused jobs are never triggered automatically, irrespective of yml configuration. You can unpause a paused job to resume automatic triggers.

<img src="/images/pipelines/pause-job.png" alt="Pause job" style="vertical-align: middle;display: block;margin-left: auto;margin-right: auto;"/>

<a name="delete"></a>
## Deleting Jobs
Deleting Job is a 2 step process. Deleting from the YML causes it to be soft deleted and then you will have to manually delete it from SPOG view of the UI. The 2 step process is an insurance policy to prevent accidental deletes. Deleting a Job means all historical versions are deleted permanently and this can really mess up your DevOps Assembly Lines as it is a connected interdependent workflow.

Here are the steps to delete a Job

1. Delete the Job definition from the YML and commit the change to the repo. Automatic sync process will execute and mark the removed Job as soft deleted. All version data is still available and no data is lost at this stage. If any Jobs are still using this deleted Job and they are still active, those Jobs will be marked inconsistent and will not be triggered until fixed
1. Now log into your SPOG, make sure that you have not hidden deleted Job from your view. All the soft deleted Jobs will appear on the bottom of your SPOG. Right click on each of them and delete. If these Jobs are still being used, then delete option is not presented until you make sure there are no references to the soft deleted Job. Once you delete from the SPOG, all data is permanently destroyed

## Further Reading
* [Jobs](/platform/workflow/job/overview)
* [Resources](/platform/workflow/resource/overview)
* [Integrations](/platform/workflow/integration/overview)
