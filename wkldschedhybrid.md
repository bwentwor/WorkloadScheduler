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


# Scheduling in a hybrid environment
{: #wkldschedhybrid}

A hybrid environment is seamlessly orchestrated partly in the cloud and party in your on-premises environment. You can create and run processes consisting of steps running partly on an agent installed in a cloud environment and partly on your local agent.

To define your workload in a hybrid environment, you must download and install the Workload Automation Agent on a local workstation with Internet access.

For example, you can use the {{site.data.keyword.workloadscheduler}} service to schedule the parsing of a file on your local file system. The result of the parsing operation can be stored locally in a file and used in a different job, for example a database job running on any agent, including the Workload Automation Agent on {{site.data.keyword.Bluemix_short}}, on-premises, or in a different cloud environment.

You can download the Workload Automation Agent from the {{site.data.keyword.workloadscheduler}} service dashboard. Scroll to the **Downloads** section and download the agent for your operating system. For more information about installing the agent, see [Installing the IBM Workload Automation on Cloud agent ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.ibm.com/support/knowledgecenter/SS4J4Z_1.0.0/com.ibm.tivoli.wasaas.doc_1.0.0/distr/src_pi/awssaaspi_installing.html).

When you install the agent, you also install the **composer** command line. The command line is especially convenient when you want to run operations in batch mode or need to make bulk changes to your scheduling definitions. For more information about using the command line to manage your workload definitions, see [**Managing scheduling definitions from the CLI** ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/support/knowledgecenter/SS4J4Z_1.0.0/com.ibm.tivoli.wasaas.doc_1.0.0/distr/src_ref/awssaasrgmanageobjs.htm).

To have the local agent communicate with the {{site.data.keyword.Bluemix_notm}} environment, open an outbound connection to https port 443 to the {{site.data.keyword.Bluemix_notm}} environment.

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

