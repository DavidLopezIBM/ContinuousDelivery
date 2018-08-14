---

copyright:
  years: 2015, 2018
lastupdated: "2018-8-2"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# {{site.data.keyword.gitrepos}}
{: #git_working}

Collaborate with your team and manage your source code with a Git repository (repo) and issue tracker that is hosted by IBM and built on [GitLab Community Edition ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://about.gitlab.com/){:new_window}.
{: shortdesc}

The {{site.data.keyword.gitrepos}} tool integration supports teams to manage code and collaborate in many ways:
   * Manage Git repositories through fine-grained access controls that keep code secure
   * Review code and enhance collaboration through merge requests
   * Track issues and share ideas through the issue tracker
   * Document projects on the wiki system

Because this tool integration is built on GitLab Community Edition and hosted by IBM on the {{site.data.keyword.Bluemix_notm}} Platform, a few GitLab options are not available. For example, Delivery Pipeline provides continuous integration and continuous delivery for {{site.data.keyword.Bluemix_notm}}; therefore, the continuous integration features in GitLab are not supported. In addition, the admin functions are not available because they are managed by IBM.
{: tip}

## Using {{site.data.keyword.gitrepos}} locally
{: #git_local}

You can locally access the Git repos that are stored in {{site.data.keyword.gitrepos}}. For instructions to set up Git locally, see [Start using Git on the command line ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://git.ng.bluemix.net/help/gitlab-basics/start-using-git){:new_window}.

{{site.data.keyword.gitrepos}} supports HTTPS connections only that use TLS1.2. If you use Eclipse to connect, you might be required to specify this protocol for your Java&trade; version by adding `-Dhttps.protocols=TLSv1.2` to your eclipse.ini file and then restarting Eclipse.
{: tip}

## Authenticating with {{site.data.keyword.gitrepos}}
{: #git_authentication}

Your {{site.data.keyword.Bluemix_notm}} login and password are only used to authenticate with {{site.data.keyword.gitrepos}} in a web browser. You cannot use your {{site.data.keyword.Bluemix_notm}} user credentials to authenticate from external Git clients. To complete remote Git operations, such as `clone` or `push`, from your local Git repo, you must use a personal access token or SSH key to authenticate with {{site.data.keyword.gitrepos}}.

### Creating a personal access token
{: #create_pat}

To authenticate with your Git repo over HTTPS, you must create a personal access token.
{: tip}

1. On the {{site.data.keyword.gitrepos}} User Settings dashboard, on the [Access Tokens page ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://git.ng.bluemix.net/profile/personal_access_tokens?cm_sp=dw-bluemix-_-nospace-_-answers){:new_window}, type the name of the application that you want to create an access token for. For example, `Git CLI`.
1. Optional: Choose an expiry date for the access token.
1. Select the **api** check box to create a personal access token that uses api as the scope.
1. Click **Create Personal Access Token**. Make note of your access token in a secure location for future use.
1. On the [Account page ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://git.ng.bluemix.net/profile/account?cm_sp=dw-bluemix-_-nospace-_-answers){:new_window}, in the Change username section, find your {{site.data.keyword.gitrepos}} username. Your username is also displayed as the first segment of the URL for any personal Git repos that you create.
1. Use your {{site.data.keyword.gitrepos}} username and personal access token to authenticate with your Git repo from an external Git client.

To learn more, see [Personal access tokens ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://git.ng.bluemix.net/help/api/README.html#personal-access-tokens){:new_window}.

### Creating an SSH key  
{:create_ssh }

To create an SSH key, see [How to create your SSH Keys ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://git.ng.bluemix.net/help/gitlab-basics/create-your-ssh-keys){:new_window}. Accessing your repositories with SSH authentication might require more configuration for proxies and firewalls.

To learn more, see [SSH ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://git.ng.bluemix.net/help/ssh/README){:new_window}.

## Physical file and repo size limits
{: #git_limits}

Files are strictly limited to 100 MB. The suggested repo size limit is 1 GB. If your repo exceeds 1 GB, you might receive an email with a request to reduce the size of the repo.

## Take a tutorial: {{site.data.keyword.gitrepos}}
{: #git_tutorials}

Check out one of these tutorials on the [IBM&reg; Cloud Garage Method ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/garage){:new_window}:

  * [Create and use your first toolchain by using the "Develop a Cloud Foundry app" toolchain ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/garage/tutorials/introduce-develop-cloud-foundry-app-toolchain){:new_window}. Learn how to create an open toolchain from a template and use the toolchain to continuously deliver a "Hello World" app.

  * [Use the "Develop and test microservices on Cloud Foundry" toolchain ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/garage/tutorials/use-develop-test-microservices-on-cloud-foundry-toolchain){:new_window}. Learn how to create a toolchain from a template with three microservices and use the toolchain to continuously deliver an online store.
