---

copyright:
  years: 2017
lastupdated: "2017-07-05"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip} 
{:download: .download}


# About {{site.data.keyword.workloadscheduler}}
{: #wkldschedovrvw}

You can use the {{site.data.keyword.workloadscheduler}} service to create, run, schedule, and monitor a set of processes that address specific needs using the {{site.data.keyword.workloadscheduler}} interface.

A **process** is a sequence of **steps** where each step performs a specific action, such as running a query or posting a message into a message queue. A process can run in different ways, on demand, according to a scheduled time, or based on a specific event, using one or more **triggers**.

Processes and steps run on **agent** workstations. An agent is a software component that can run your processes and steps and is either maintained in the {{site.data.keyword.Bluemix}} environment or installed on your local workstation. When you install the agent locally, you set up a hybrid environment, in which processes and steps are orchestrated to run partly in the cloud and partly in your on-premises environment. You can also deploy a container with the IBM Scheduler agent images installed and configured to connect to the {{site.data.keyword.workloadscheduler}} {{site.data.keyword.Bluemix_notm}} service.

For example, you can use the {{site.data.keyword.workloadscheduler}} service to schedule the parsing of a file on your local file system. The result of the parsing operation can be stored locally in a file and used in a different job, for example a database job running on any agent, including the Workload Automation Agent on {{site.data.keyword.Bluemix_notm}}, on-premises, or in a different cloud environment.

For more information, see [Scheduling in {{site.data.keyword.Bluemix_notm}}](wkldscheddocker.html), [Scheduling in a hybrid environment](wkldschedhybrid.html), and [Scheduling with IBM Containers for {{site.data.keyword.Bluemix_notm}}](docker_image_workloadscheduler/wkdlsched_starter.html).

After being created, a process must be enabled on the server before it can be triggered to run according to the specified schedule.

Any processes that you create can be organized into categories in the **Process Library**. Each individual step in a process can be run on different agents, even if those agents have different operating systems, to easily integrate with legacy applications.

The {{site.data.keyword.workloadscheduler}} service also provides a more sophisticated environment in which you can orchestrate complex process flows, apply conditional branching logic, use What-if predictive analytics on your workload, and many more features. For more information, see [Advanced scheduling environment](wkldschedadvanced.html).

You can create and manage processes also using the related REST APIs. REST APIs give you programmatic access to the {{site.data.keyword.workloadscheduler}} service. You import or reference the provided REST API libraries before your application can interact with them. To make coding against these REST APIs easier, the {{site.data.keyword.workloadscheduler}} service provides client libraries that can reduce the amount of code you need to write and make your code more robust.

All necessary information about creating and running steps in {{site.data.keyword.Bluemix_notm}} are available in the [{{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggerdwc) and [{{site.data.keyword.workloadscheduler}} advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggereng).

API client libraries are provided in the [Scheduling in {{site.data.keyword.Bluemix_notm}}](wkldscheddocker.html#) section to help you create your {{site.data.keyword.workloadscheduler}} service and add it to your applications. The following runtimes are supported:

-   **Java™**
-   **Node.js**
-   **Ruby**
-   **PHP**
-   **Python**

## Related Links
{: #rellinks}

**Tutorials and Samples**  


[HelloWorkload sample app ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/WAdev0/HelloWorkloadSampleApp)

[Exploring new business opportunities with {{site.data.keyword.workloadscheduler}} Service for {{site.data.keyword.Bluemix}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.youtube.com/watch?v=N3u8pZrehNo)

[{{site.data.keyword.workloadscheduler}} for {{site.data.keyword.Bluemix_notm}} integration with Liberty for Java ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://youtu.be/hKYxMVoH-yE)

[{{site.data.keyword.workloadscheduler}} integration with BigInsights for Hadoop ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.youtube.com/watch?v=GUx35YDf5bo)

[Stock Compare application ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/WAdev/StockCompare-Java)

**SDK**  




**API Reference**  


!prod![{{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggerdwc)!!prod!

<!-- STAGING[{{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://wastagdal05sand.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggerdwc)-->

!prod![{{site.data.keyword.workloadscheduler}} advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggereng)!!prod!

<!-- STAGING[{{site.data.keyword.workloadscheduler}} advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://wastagdal05sand.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggereng)-->

**Compatible Runtimes**  
This section contains the links to the client libraries, both advanced and UI, for all compatible runtimes   


[Client libraries for Java for advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-advanced-java.zip)

[Client libraries for Node.js for advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-advanced-nodejs.zip)

[Client libraries for PHP for advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-advanced-php.zip)

[Client libraries for Python for advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-advanced-python.zip)

[Client libraries for Ruby for advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-advanced-ruby.zip)

[Client libraries for Java for {{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-light-java.zip)

[Client libraries for Node.js for {{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-light-nodejs.zip)

[Client libraries for PHP for {{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-light-php.zip)

[Client libraries for Python for {{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-light-python.zip)

[Client libraries for Ruby for {{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/iws-light-ruby.zip)

[Client libraries for Java - APIs for the earlier version ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/ClientLibraries_java.zip)

[Client libraries for Node.js - APIs for the earlier version ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/bluemix/ClientLibraries_nodejs.zip)

**Related Links**  


[{{site.data.keyword.Bluemix_notm}} development community ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/bluemix/support/)

[{{site.data.keyword.Bluemix}} Prerequisites ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.ng.bluemix.net/docs/overview/whatisbluemix.html#bluemixoverview)

[Workload Automation (SaaS) overview ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibmserviceengage.com/workload-automation/learn)

[Workload Automation (SaaS) product documentation ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www-01.ibm.com/support/knowledgecenter/SS4J4Z_1.0.0/com.ibm.tivoli.wasaas.doc_1.0.0/saas_landing.html)

[{{site.data.keyword.Bluemix_notm}} Pricing Sheet ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud-computing/bluemix/pricing/)

