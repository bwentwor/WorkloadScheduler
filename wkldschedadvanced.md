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


# Advanced scheduling environment
{: #wkldschedadvanced}

You can use the {{site.data.keyword.workloadscheduler}} service to create, run, schedule, and monitor a set of processes that address specific needs using the {{site.data.keyword.workloadscheduler}} user interface.

In addition to using the {{site.data.keyword.workloadscheduler}} user interface to manage simple processes which do not require advanced scheduling, you can use the Dynamic Workload Console to orchestrate complex process flows, apply conditional branching logic, and use What-if predictive analytics on your workload, and many more features.

The Dynamic Workload Console is a fast, powerful, and user-friendly interface of operational control for your entire Workload Automation scheduling environment. With the Dynamic Workload Console, you can define, edit, and monitor your automated workflow.

The Dynamic Workload Console processes are named job streams and the steps are named jobs.

The Dynamic Workload Console provides the following advantages:

Parallel flows:

   Jobs belonging to a job stream can run in parallel mode. You can use conditions or dependencies between jobs to build your workflow.

Reuse:

   When a job is defined, its options are saved in a job definition that can be re-used across different flows.

Flexibility:

   For each job in a job stream, you can set several dependencies and conditions. For example, you can set complex conditions such as triggering jobs to run when others have completed successfully, or when a specific file is created.

More scheduling options:

   Plan when to run your jobs by setting a run cycle that specifies on which days to run the job stream. For example, tomorrow, next week, next year, weekends, the second Friday in every month.

Graphical view:

   Use the graphical view to show your workflow in a graph. This view shows the selected job stream with all the jobs it contains and their associated dependencies.

For more information, see [Dynamic Workload Console User's Guide ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www-03preprod.ibm.com/support/knowledgecenter/SS4J4Z_1.0.0/com.ibm.tivoli.wasaas.doc_1.0.0/distr/src_tsweb/General_Help/tswebmst.html).

You can also use your {{site.data.keyword.workloadscheduler}} service on your mobile device using the Self-Service Catalog and Self-Service Dashboard applications. For more information, see [Mobile Applications User's Guide ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.ibm.com/support/knowledgecenter/SSGSPN_9.4.0/com.ibm.tivoli.itws.doc_9.4/common/src_md/awsmdmst_welcome.html).

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

[{{site.data.keyword.Bluemix_short}} Pricing Sheet ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud-computing/bluemix/pricing/)

