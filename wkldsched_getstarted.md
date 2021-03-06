---

copyright:
  years: 2018
lastupdated: "2018-08-03"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip} 
{:download: .download}


# Scheduling with IBM Cloud Kubernetes Service for {{site.data.keyword.Bluemix_notm}}
{: #gettingstarted}


You can use the IBM Scheduler agent image from the {{site.data.keyword.Bluemix_short}} catalog to create a single container.

You can deploy a container with the IBM Scheduler agent image installed and configured to connect to the {{site.data.keyword.workloadscheduler}} {{site.data.keyword.Bluemix_notm}} service. The {{site.data.keyword.workloadscheduler}} image (**registry.bluemix.net/ibm_wa_agent**) is supplied for IBM Cloud Kubernetes Service for {{site.data.keyword.Bluemix_notm}}. For more information about {{site.data.keyword.Bluemix_notm}} Kubernetes Service, see the relevant documentation.

The IBM Scheduler agent image provides the following software package:

-   {{site.data.keyword.workloadscheduler}} dynamic agent, at the latest released version.

You can use the IBM Scheduler agent image from the {{site.data.keyword.Bluemix_notm}} catalog to create a single container.

The following prerequisites are required:

-   {{site.data.keyword.Bluemix_notm}} CLI
-   Container service plugin

For more information about the {{site.data.keyword.Bluemix_notm}} CLI, see the documentation about getting started with {{site.data.keyword.Bluemix_notm}} CLI.
 
Perform the following steps:

 1.  Instance a {{site.data.keyword.workloadscheduler}} service.
    
 2.  Login to {{site.data.keyword.Bluemix_notm}} using your account credentials. For example, to login to the US South region, type the following command:
    
    `ibmcloud login -a https://api.ng.bluemix.net`
    
 3.  Set your {{site.data.keyword.Bluemix_notm}} region by selecting a region from the on-screen list:
    
    `ibmcloud cs region-set`
    
 4.  Set an organization and a space:
    
    `ibmcloud target -o <OrgName> -s <SpaceName>`

 5. Create a cluster, if you do not have one already available. See the {{site.data.keyword.Bluemix_notm}} documentation about setting up clusters.
 
 6. List available clusters:
 
  `bx cs clusters`
  
 7. Configure your cluster and follow the on-screen instructions in order to export the KUBECONFIG variable:
  `ibmcloud cs cluster-config <your_cluster_name>`
  
 8. List available {{site.data.keyword.Bluemix_notm}} services:
   `ibmcloud service list`
 
 9. Set your secret token: 
    `bx iam oauth-tokens`
    
 10. Bind your cluster service to your service name:
 
 `ibmcloud cs cluster-service-bind <your_cluster_id> default <your_service_name>`
       where <dl>
  <dt><strong>your_cluster_id</strong></dt>
  <dd>is the ID of your cluster.</dd>
  <dt><strong>your_service_name</strong></dt>
  <dd>is the name of your service.</dd>
 </dl>

 11. Check that the Kubernetes secret was created:

    `kubectl get secrets --namespace=default`

 12. Deploy your IBM Scheduler agent on your cluster using the yaml file:

    `kubectl apply -f <yaml_file>`
    
Your IBM Scheduler agent is now up and running.

The following example contains a sample yaml file, which you can customize as necessary and use to deploy the IBM Scheduler agent on your cluster, as described in step 12: 

    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      labels:
        app: agent
      name: agent
      namespace: default
    spec:
      selector:
        matchLabels:
          app: agent
      replicas: 1
      template:
        metadata:
          labels:
            app: agent
        spec:
          containers:
          - image: registry.bluemix.net/ibm_wa_agent
            name: agent
            resources:
              limits:
                cpu: 1000m
                memory: 500Mi
            env:
            - name: AGENTNAME
              value: <agent_workstation_name>
            volumeMounts:
            - mountPath: /opt/service-bind
              name: service-bind-volume
          imagePullSecrets:
          - name: private-registry
          volumes:
          - name: service-bind-volume
            secret:
              defaultMode: 420
              secretName: <secret_name> 

 where <dl>
  <dt><strong>agent_workstation_name</strong></dt>
  <dd>is the name of the workstation where the agent is installed.</dd>
  <dt><strong>secret_name</strong></dt>
  <dd>is the name of your secret. To obtain this name, use the **kubectl get secrets** command.</dd>
  </dl>
  
The following example contains a sample yaml file with persistent storage, which you can customize as necessary and use to deploy the IBM Scheduler agent on your cluster, as described in step 12: 

    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      name: workload-automation-claim
      annotations:
       volume.beta.kubernetes.io/storage-class: "<storage_class_name>"
     spec:
      accessModes:
       - ReadWriteOnce
      resources:
       requests:
        storage: <volume_size>
        
    apiVersion: extensions/v1beta1
    kind: Deployment
    metadata:
      labels:
       app: agent
      name: agent
      namespace: default
    spec:
      selector:
        matchLabels:
          app: agent
      replicas: 1
      template:
        metadata:
          labels:
            app: agent
        spec:
          containers:
          - image: registry.bluemix.net/ibm_wa_agent
            name: agent
            resources:
              limits:
                cpu: 1000m
                memory: 500Mi
            env:
            - name: AGENTNAME
              value: <agent_workstation_name>
             volumeMounts:
             - mountPath: /opt/service-bind
             name: service-bind-volume
             - mountPath: /home/wauser/TWA/TWS/stdlist
             name: workload-automation-volume
          imagePullSecrets:
          - name: private-registry
          volumes:
          - name: service-bind-volume
            secret:
              defaultMode: 420
              secretName: <secret_name>
           - name: workload-automation-volume
            claimName: workload-automation-claim
 

 where <dl>
  <dt><strong>storage_class_name</strong></dt>
  <dd>is the name of the storage class you will use for your claim. Additional information can be found at the following link: [Persistent volumes and persistent volume claims](https://console.bluemix.net/docs/containers/cs_storage_basics.html#pvc_pv) </dd>
  <dt><strong>agent_workstation_name</strong></dt>
  <dd>is the name of the workstation where the agent is installed.</dd>
  <dt><strong>secret_name</strong></dt>
  <dd>is the name of your secret. To obtain this name, use the **kubectl get secrets** command.</dd>
  </dl>
  
    
  Evaluate the volume_size variable with the following formula:

`Volume size(MB)= 120 + [ 30 x  <jobs_per_day> x (<average_joblog_size_MB> / 3 + 0.008) ]`

For example, considering “average_joblog_size_MB = 0.001 MB (1KB)”, you obtain:

   `1.000 jobs_per_day:  370 MB     -->          volume_size = 370Mi`
   
   `10.000 jobs_per_day:  2.6 GB    -->          volume_size = 2600Mi`
    
   `100.000 jobs_per_day: 25 GB     -->          volume_size = 25Gi`
   
   
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

