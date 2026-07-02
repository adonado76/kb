---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Referência de permissões somente leitura Amazon Web Services"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conexão com AWS - Guia de integração do cliente"
  - "Referência de permissões Amazon Web Services"
source_path: "admin/read-only-permissions-aws.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Referência de permissões somente leitura Amazon Web Services

As seguintes permissões de somente leitura estão disponíveis para AWS em Cloudability Premium :

- autoscaling:DescribeAutoScalingGroups
- autoscaling:DescribeLaunchConfigurations
- autoscaling:DescribeTags
- ce:GetReservationUtilization
- ce:GetSavingsPlansPurchaseRecommendation
- ce:GetSavingsPlansUtilizationDetails
- cloudtrail:LookupEvents
- cloudwatch:GetMetricData
- cloudwatch:GetMetricStatistics
- cloudwatch:GetMetricStatistics
- cloudwatch:ListMetrics
- cloudwatch:ListTagsForResource
- dynamodb:DescribeTable
- dynamodb:ListTables
- ec2:DescribeAccountAttributes
- ec2:DescribeAddresses
- ec2:DescribeInstanceAttribute
- ec2:DescribeAvailabilityZones
- ec2:DescribeImages
- ec2:DescribeInstances
- ec2:DescribeInstanceTypeOfferings
- ec2:DescribeInstanceTypes
- ec2:DescribeLaunchTemplateVersions
- ec2:DescribeRegions
- ec2:DescribeReservedInstances
- ec2:DescribeReservedInstancesModifications
- ec2:DescribeSnapshots
- ec2:DescribeSpotInstanceRequests
- ec2:DescribeSpotPriceHistory
- ec2:DescribeTags
- ec2:DescribeVolumes
- ec2:DescribeVolumesModifications
- ec2:DescribeVolumeStatus
- ec2:GetReservedInstancesExchangeQuote
- ecs:DescribeClusters
- ecs:DescribeContainerInstances
- ecs:ListClusters
- ecs:ListContainerInstances
- elasticache:DescribeCacheClusters
- elasticache:DescribeReservedCacheNodes
- elasticache:ListTagsForResource
- elasticmapreduce:DescribeCluster
- elasticmapreduce:ListClusters
- elasticmapreduce:ListInstances
- iam:GetUser
- iam:SimulatePrincipalPolicy
- lambda:ListFunctions
- lambda:ListProvisionedConcurrencyConfigs
- organizations:DescribeOrganization
- organizations:ListAccounts
- organizations:ListAccounts
- organizations:ListTagsForResource
- pi:GetResourceMetrics
- pi:ListAvailableResourceMetrics
- pricing:DescribeServices
- pricing:GetAttributeValues
- rds:DescribeDBClusters
- rds:DescribeDBInstances
- rds:DescribeDBParameters
- rds:DescribeOrderableDBInstanceOptions
- rds:DescribeReservedDBInstances
- rds:ListTagsForResource
- redshift:DescribeClusters
- redshift:DescribeClusterSnapshots
- redshift:DescribeReservedNodes
- redshift:DescribeTags
- s3:GetBucketAcl
- s3:GetObject
- s3:ListAllMyBuckets
- s3:ListBucket
- savingsplans:DescribeSavingsPlans
- savingsplans:DescribeSavingsPlansOfferingRates
- eks:DescribeCluster
- eks:DescribeNodegroup
- eks:ListClusters
- eks:ListNodegroups
- rds:DescribeBlueGreenDeployments
- rds:DescribeGlobalClusters

**Tópico principal:** [Referência de permissões Amazon Web Services](../admin/permissions-reference-aws.html)
