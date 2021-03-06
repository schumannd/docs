page_main_title: Managing nodes
main_section: Platform
sub_section: Tutorials
sub_sub_section: Runtime

# Managing your build infrastructure

You can configure your build infrastructure and manage it through your Subscription's **Settings** tab. You can add as many nodes to your subscription as the number of minions in your billing plan.

Once you add you nodes, there is very little management required from you to keep them running. Once in a while, you might be asked to reset or upgrade your nodes but this is usually achieved in a few minutes.

The following guides will help you manage your build infrastructure:

* [Adding a node](#add-node)
* [Editing a node](#edit-node)
* [Resetting a node](#reset-node)
* [Deleting a node](#delete-node)


<a name="add-node"></a>
##Adding a build node
Follow the steps below to add a build node:

- From your Dashboard, click on Subscriptions in the left sidebar menu and click on your subscription.
<img width="30%" height="30%" src="/images/platform/integrations/list-subscriptions.png" alt="List subscriptions">
- Click on the **gear icon** on the Subscription page and then on **Nodes**.
- Choose the radio button for **Custom**.
<img src="../../images/getting-started/byon-select-my-node.png" alt="bring your own node">
- To add a build machine, click on the **+** button in the **NODE LISTS** section. You will be redirected to the Add Node page.
- Select the OS of the nodes you want to add.
- Enter a name for the node and its IP address.
<img src="../../images/getting-started/byon-name-ip.png" alt="Enter name and IP">
- Click on the **Docker version** dropdown and select the version you want installed on your nodes. Please note that the list of available versions is populated based on your choice of OS.
- You can choose to initialize the build host through Shippable or run the initialization scripts yourself. Initialization through Shippable requires you to grant SSH access, so if you do not want to grant that for any reason, select the radio button for `Manual (script based)`

* To initialize the node through Shippable,
    * Enter the SSH port for your build host. This is usually port 22, but is configurable.
    * Choose whether you want to enable swap space on your machine.
    * Copy the command shown and run it on your build host. This will create a
    shippable user on your host and allow us to run initialization scripts on
    your machine.
    * Check the checkbox to confirm that you have run the command on your machine
    and click on `Initialize`
    * You will be redirected to a page showing you the console log as your machine
    is initialized.
    * When your node is ready, the status indicator for the node will turn green. Your node is now ready to pick up builds for your projects.

<img src="../../images/getting-started/intialize-byon-shippable.png" alt="Select docker version">


* To run the initialization scripts yourself,
    * Choose whether you want to enable swap space on your machine.
    * Click on **Generate initialization scripts** to generate the script.
    * Click on **Download scripts** to download. Copy it to your build machine and
    run them.
    * Check the **I have run this script on my node successfully** and then click
    on the **Save** button.
    * Your node status will automatically show green at this point. We have no way F
    of verifying that the node was in fact successfully initialized so you will
    need to make sure this was the case.

Once you add your first build node, all subsequent builds for that subscription
will run on your machines. Your nodes can be seen by going to your Subscription Settings and clicking on **Nodes** in the left sidebar menu.

<img src="../../images/getting-started/list-byon-nodes.png" alt="Select docker version">

<a name="edit-node"></a>
##Editing a build node

- From your Dashboard, click on Subscriptions in the left sidebar menu and click on your subscription.
<img width="30%" height="30%" src="/images/platform/integrations/list-subscriptions.png" alt="List subscriptions">
- Click on the **gear icon** on the Subscription page and then on **Nodes**.
- Click on the node in the **NODE LISTS** section.
- You can click on the **Edit** button for a build node to edit the node name. Nothing
else can be edited for a node.

<a name="reset-node"></a>
##Resetting a build node

- From your Dashboard, click on Subscriptions in the left sidebar menu and click on your subscription.
<img width="30%" height="30%" src="/images/platform/integrations/list-subscriptions.png" alt="List subscriptions">
- Click on the **gear icon** on the Subscription page and then on **Nodes**.
- Click on the node in the **NODE LISTS** section.
- You can reset a node by clicking on the **Re-initialize** button. This action will initialize/install everything from scratch.

If you have added your own build nodes, you will need to re-download the initialization script and run it on your node.

<a name="delete-node"></a>
##Deleting a build node

- From your Dashboard, click on Subscriptions in the left sidebar menu and click on your subscription.
<img width="30%" height="30%" src="/images/platform/integrations/list-subscriptions.png" alt="List subscriptions">
- Click on the **gear icon** on the Subscription page and then on **Nodes**.
- Click on the node in the **NODE LISTS** section.
- Scroll to the bottom of the screen and click on **Delete** to delete your build node. This action is final and cannot be undone.
