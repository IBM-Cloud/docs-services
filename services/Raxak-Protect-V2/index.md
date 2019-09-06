---

copyright: 

  years:  2019

lastupdated: "2019-09-05"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Raxak Protect V2
{: #gettingstarted_raxak_protect_v2}

Raxak Protect allows IBM Hybrid Cloud users to automatically and uniformly configure the security of their servers according to industry best practices and regulatory guidelines.

{:shortdesc}

## Getting started
Once you have subscribed to the service, you will be redirected to the Raxak Protect dashboard.

If needed, you may log in with your IBM ID by clicking on the IBM Cloud logo.

Keep the following definitions in mind:
* A *resource* is a computing instance.  Some examples include: a Linux or Windows server, a database image, a web application server, etc.  As of the date of this document, we only support compute servers.  In Cloud Raxak portals, we refer to resources in context of security configuration management for those resources.
* A *profile* is set of rules that collectively define a security posture (some standard profiles include DISA-MCC, PCI-DSS, ISO27002, etc.).  Each profile has a strength that indicates how comprehensive the profile is in securing resources, as compared to a comprehensive security profile Cloud Raxak has created based on DISA’s latest release of the Mission Critical Classified profile (note that we have set the Profile Strength of our DISA-MCC profile to 100%).  Keep in mind that you can have a profile with a strength greater than 100% if that profile is stronger than our standard DISA-MCC profile.
* Each *rule* in a profile specifies a particular OS or application-specific configuration parameter and its desired setting.  For example, one rule can say that the password length for user authentication should be greater than 14 characters.  Rules are also tagged by severity from Low to High, which indicates the degree of vulnerability that your resource is exposed to if the configuration specified by that rule is improperly set.
* A *profile application* is the process of applying a security profile to a resource at a specified frequency.  Each profile application can contain multiple runs (defined below).  Each profile application consists of these attributes: Schedule Start Date, Schedule End Date, Compliance Frequency, Compliance Mode, and Rule Exceptions. Note that a profile can also be applied as a single application (Apply Now), or a deferred single application (Apply Later). In these cases, the Schedule Start Date and the Schedule End Date are the same.

For Raxak Protect to be able to access, scan, and remediate your resources, your networks need to be configured to allow Cloud Raxak’s servers to reach your resources and connect to them over SSH or WinRM. We connect from our IBM Cloud service endpoint at 169.45.81.142, using port 22 for SSH (to your Linux servers) and port 5986 for WinRM (for your Windows servers). In addition your server must be able to reach the our service endpoint at https://raxakprotect.cloudraxak.net over port 443 using the HTTPS protocol to allow it to enroll in the Raxak Protect service.

The key steps to follow in enrolling your first resource are:
1. Download an enrollment script by selecting **Resource Management** -> **Enroll Resource** from the left hand navigation pane. Specify what kind of resource you want to enroll, and if you want any scanning or remediation done automatically on that resource.
2. Copy the downloaded script (via scp or similar tools) to the server you want to enroll.
3. Execute the script as root (via sudo for example) if it is a Linux server, or as Adminstrator using PowerShell if it is a Windows Server.
4. You will see the enrolled server in the **Manage Resources** tab accessible from the left hand navigation pane.
5. You can apply a profile to the resource from the **Secure My Environment** -> **Secure Resource** link in the left hand navigation pane.
6. Once profile application is complete (as shown in the **Manage Resources** pane, you can see the results of the profile application from the **Compliance Governance** -> **Resource Health** pane. Alternately you can click on the computer monitor icon on the right edge of the relevant resource in the **Manage Resources** pane and jump directly to the last known resource health report.




See https://docs.google.com/document/d/e/2PACX-1vQymvky7ote4IduAs1H4LhkjeH54OcZ5Sm5uFRffGyrl3gAnRfdMfA5MicvjNyq3c-OdyHqxbZ7onpR/pub for more details.


