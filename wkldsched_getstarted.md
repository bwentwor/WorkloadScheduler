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


# Scheduling with IBM Containers for {{site.data.keyword.Bluemix_notm}}
{: #gettingstarted}

You can use one of the IBM Scheduler agent images from the {{site.data.keyword.Bluemix_short}} catalog to create a single container.

You can deploy a container with the IBM Scheduler agent images installed and configured to connect to the {{site.data.keyword.workloadscheduler}} {{site.data.keyword.Bluemix_notm}} service. The {{site.data.keyword.workloadscheduler}} images are supplied for IBM Containers for {{site.data.keyword.Bluemix_notm}}.

Every IBM Scheduler agent image provides the following software package.

-   {{site.data.keyword.workloadscheduler}} dynamic agent, at the latest released version.

You can use one of the IBM Scheduler agent images from the {{site.data.keyword.Bluemix_notm}} catalog to create a single container.

1.  Instance a {{site.data.keyword.workloadscheduler}} service.
2.  From the {{site.data.keyword.Bluemix_notm}} menu, click Containers, then IBM Public Repositories. The IBM Scheduler agent image is located in this page: [https://console.bluemix.net/containers-kubernetes/home/registryPublicImages/ ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/containers-kubernetes/home/registryPublicImages/) with the name ibm_wa_agent.
3.  To build your container, select the IBM Scheduler agent image The container creation page opens.
4.  Create the container.
    1.  Select one of the {{site.data.keyword.Bluemix_notm}} spaces in your environment.
    2.  In the **Container name** field, enter the name for the container.
    3.  In the **Size** field, select a container size. The suggested minimum size is **Medium** (1 GB Memory, 10 GB Storage).
5.  Expand **Advanced Options** to add a volume, add environment variables, or bind a {{site.data.keyword.Bluemix_notm}} service.
    1.  Add a volume. To persist agent data, select **Create a volume** if this is the first time you are provisioning the agent, then select **Assign an existing volume**. If the agent has been previously created, skip to **Assign an existing volume**.

        To create the volume:
           1.  Select **Create a volume**.
2.  Specify a volume name and optionally a file share.
        To assign the volume to the container:
           1.  Select **Assign an existing volume**.
2.  Select the volume you created previously from the list to assign the volume to the container and specify the following path: /home/wauser/TWA/TWS/stdlist.
    2.  Define an environment variable to assign a name to the agent.
        1.  Click **Add a new environment variable**.
        2.  Specify AGENTNAME as the environment variable name in the field on the left, and specify a value for the variable in the field on the right.

            **Important:**

            -   During the agent registration, the system automatically adds three characters to the beginning of the value specified as the agent name.
            -   The maximum supported length for the agent name is 13 characters.
6.  Bind the IBM Scheduler agent to your instance of the {{site.data.keyword.workloadscheduler}} service, selecting the service from the list and clicking **Add**.
7.  Click **Create** to initiate the provisioning of the IBM Scheduler agent The agent is ready to be started and used after a few seconds.

## Updating the IBM Scheduler agent
{: #agentupgrade}

You can update your IBM Scheduler agent with the most recent image version available only if you have used a persistent data volume during the creation of the container.

To update the IBM Scheduler agent with the most recent image version:

1.  Stop and delete the container.
2.  Repeat the steps for creating a container outlined in [Scheduling with IBM Containers for {{site.data.keyword.Bluemix_notm}}](#) to create a new container using the most recent agent image available. When prompted, specify the existing volume created for the original container.

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


[{{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggerdwc)

<!-- STAGING[{{site.data.keyword.workloadscheduler}} UI APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://wastagdal05sand.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggerdwc)-->

[{{site.data.keyword.workloadscheduler}} advanced APIs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://start.wa.ibmserviceengage.com/ibm/TWSSandbox/wa/wa_sandbox_proxy_v2.jsp?t=swaggereng)

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

[{{site.data.keyword.Bluemix}} Prerequisites ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/bluemix/support/#prereqs)

[Workload Automation (SaaS) overview ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibmserviceengage.com/workload-automation/learn)

[Workload Automation (SaaS) product documentation ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www-01.ibm.com/support/knowledgecenter/SS4J4Z_1.0.0/com.ibm.tivoli.wasaas.doc_1.0.0/saas_landing.html)

[{{site.data.keyword.Bluemix_notm}} Pricing Sheet ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.%7Bng.bluemix.net%7D/pricing/)

