---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Provisioning"
breadcrumb:
  - "Cloudability API"
  - "Containers End Points"
  - "Provisioning"
source_path: "SSVCLNQ/api-v3/provisioning.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Provisioning

Summary

Any cluster that you would like Cloudability 's Container Cost Allocation tool to report on must first be provisioned. The provisioning process generates credentials as well as a Kubernetes deployment config that should then be installed in the cluster. The deployment will launch the Cloudability Metrics Agent in the cluster, into its own namespace. The Metrics Agent will then gather information about the cluster periodically, and send it back to Cloudability.

The provisioning end points provide API access to the provisioning process.

Learn more about provisioning a Kubernetes cluster.

End Point

/containers/provisioning

Query Arguments

| Parameter | Required | Type | Description |
| --- | --- | --- | --- |
| clusterName | Yes | string | Name of the cluster to be provisioned (must be unique, and cannot be modified) |
| kubernetesVersion | This OR clusterVersion is required but not both | string | The version of Kubernetes that is running on the cluster to be provisioned. |
| clusterVersion | This OR kubernetesVersion is required but not both | String | The version the cluster is running on being provisioned. |

Valid clusterVersion strings include OpenShift and Kubernetes. In the format: "openshift_x.xx" and "kubernetes_x.xx"

Provisioning a Cluster

When you have a new cluster that you'd like to see in the Cloudability Container Allocation tool, you will need to deploy the IBM FinOps Agent into the cluster. The provisioning API allows you to let Cloudability know about the cluster by "provisioning" it via this API. Once provisioned, the API can then produce the deployment helm for you to deploy the IBM FinOps Agent to the new cluster.

Below is the sample curl

```
curl --request POST \
  --url https://api.cloudability.com/v3/containers/provisioning/v2/helm \
  --header 'Content-Type: application/json' \
  --header 'apptio-environmentid: XXX' \
  --header 'apptio-opentoken: XXX' \
  --data '{
	"clusterName": "Test-Cluster-Name",
	"clusterVersion": "1.31"
}'
```

```
{"result":
"helm install ibm-finops-agent ibm-finops/finops-agent 
--set agent.kubecost.enabled=false
 --set agent.cloudability.uploadRegion=<region> 
--set agent.cloudability.parseMetricsData=false 
--set agent.cloudability.secret.create=true 
--set agent.cloudability.secret.cloudabilityAccessKey='<key>' 
--set agent.cloudability.secret.cloudabilitySecretKey='<key>' 
--set agent.cloudability.secret.cloudabilityEnvId='id'
--set clusterId='<clusterName>' 
--create-namespace -n ibm-finops-agent "
}
```

Below is the curl to get yaml to provision a cluster for old metrics agent

```
curl -X POST "https://api.cloudability.com/v3/containers/provisioning?pretty" \\
-u "${API_KEY}:" \\
-H "Content-type: application/json" \\
--data-binary '{
 "clusterName":"myTestCluster",
 "kubernetesVersion":"1.11"
}'
```

```
{
  "result": {
    "id": 1,
    "clusterName": "myTestCluster",
    "createdAt": "2018-05-18T15:40:23.29551Z",
    "kubernetesVersion": "1.11",
   }
}
```

Now, the cluster has been added to our database and a kubernetes deployment configuration has been generated. Note the "id" in the response. Use that in the following examples where "$" is in the uri.

To retrieve the deployment configuration yaml:

```
curl "https://api.cloudability.com/v3/containers/provisioning/${ID}/config" \\
-u "${API_KEY}:"
```

The output is a kubernetes deployment yaml file that will deploy the Cloudability Metrics Agent to your new cluster (follow whatever process is typical for your company to deploy new services to the cluster).

List All Provisioned Clusters

```
curl "https://api.cloudability.com/v3/containers/provisioning?pretty" \\
-u "${API_KEY}:"
```

Update Provisioned Cluster

You can also update the provisioning details for a cluster. For example, request to update the kubernetes version to 1.12 for a cluster:

```
curl "https://api.cloudability.com/v3/containers/provisioning/${ID}?pretty" \\
-XPUT \\
-u "${API_KEY}:" \\
-H "Content-type: application/json" \\
--data-binary '{"kubernetesVersion":"1.12"}'
```

Once updated, you can fetch the updated deployment configuration through the same method as above, and then re-deploy the configuration to your cluster to update the Cloudability Metrics Agent.

Note: clusterName is read-only once created and cannot be modified. Further, you currently must provide ALL the other fields (even those not changing), otherwise they will be updated to whatever the default for the type is. Support for PATCH is coming, which will allow for only specifying the fields that are changing.
