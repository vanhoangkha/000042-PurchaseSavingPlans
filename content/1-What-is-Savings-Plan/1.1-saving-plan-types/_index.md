+++
title = "Saving Plan Types"
weight = 1
chapter = false
pre = "<b>1.1 </b>"
+++

#### Compute Savings Plan
**Compute Savings Plan** is the best and most flexible solution to use the service, saving 60% compared to the cost of using **On-Demand** services.
  The SP is automatically applied to EC2 instances, regardless of the Instance's family, Instance size, region, operating system, or tenancy type. The same is true for services like Fargate and Lambda.

  With this type of charging, we can move workloads from C5 to M5, move traffic from Ireland to London, or move applications from EC2 to Fargate at any time.
  You still benefit from Savings Plan's low-cost calculation when you make changes to the system's services.

#### EC2 Instance Savings Plan
**EC2 Instance Savings Plan** solution saves costs up to 72%, in exchange for committing to using a specific family of Instances in a specific Regions.
  These plans automatically apply regardless of capacity, operating system or tenancy type, as long as the Instance family stays the same and the Regions are not changed.

{{% notice tip %}}
As we can see, EC2 Instance Savings Plan gives us a higher discount and Compute Savings Plan gives us a more flexible choice of resource type switching.
{{% /notice %}}