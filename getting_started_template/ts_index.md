{:tsSymptoms: .tsSymptoms} 
{:tsCauses: .tsCauses} 
{:tsResolve: .tsResolve} 
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# <service_short_name> troubleshooting
{: #ts}
<!-- Provide an appropriate ID above -->
*Last updated: nn month yyyy*
{: .last-updated}

<!-- This is the template for troubleshooting topics.  -->

<!-- The short description section should include the service long name for search optimization. Example short description: -->

Here are the answers to common troubleshooting questions about using <service_name.
{:shortdesc}


<!-- Example problem statement title: "Cannot add Git repository" -->

## <problem_statement>
{: #problem}

<!-- This is the template for a problem topic.  -->

<!-- The short description section contains a brief description of problem. For example:  -->

After you create an app on the Dashboard, you click *ADD GIT* to create a Git repository, but you cannot proceed.
{:shortdesc}

<!-- The symptoms section contains a description of problem symptoms. For example:  -->
When you click ADD GIT, a window opens and one of these issues occur:
- The window hangs with a blank screen.
- A message states that a problem exists with 3rd party cookies.
{: tsSymptoms}

<!-- The causes section contains a brief explanation of what causes the problem. For example:  -->
Your browser might be configured to prevent a cookie from being set. That cookie must be set from the IBM Bluemix DevOps Services site in the hub.jazz.net internet domain from within the context of the Bluemix console.
{: tsCauses}

<!-- The resolve section contains steps to resolve the problem. For example:  -->
You can fix this problem in one of three ways:
- Follow the instructions that are in the window that opens from the Bluemix console. Click the button. Another browser window opens temporarily. In that window, DevOps Services sets the authentication cookie.
- In another browser tab, go to https://hub.jazz.net and log in. Return to the Bluemix console and refresh the page. Click ADD GIT again.
- Change your browser settings to enable 3rd party cookies and click ADD GIT again. 
{: tsResolve}

## <service_name> error messages
{: #errormsgs}

You might see these error messages when using the <service_name> service on Bluemix.
{:shortdesc}

### errorID
**message description**

Message explanation (optional)

Recovery

### BXNUI0001E
**The page wasn't loaded because Bluemix didn't detect whether a session exists.** 

For instructions to fix this problem, see this [troubleshooting topic](https://www.{DomainName}/docs/troubleshoot/accessing.html#tr_err){: new_window}.
