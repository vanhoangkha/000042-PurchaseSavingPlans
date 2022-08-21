+++
title = "Reserved Instance type"
weight = 1
chapter = false
pre = "<b>4.1 </b>"
+++


#### Reserved Instance Types
There are two main types of RIs: Standard (**Standard**) and Portable (**Convertible**)

| Features                                                                                                | Standard                                            | Convertible                                         |
|---------------------------------------------------------------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------|
| Ability to save (compared to On-Demand) | 1 year (40%), 3 years (60%) | 1 year (31%), 3 years (54%) |
| Change Availability Zone, instance size (Linux OS), networking type. V/d: from t2.medium –> t2.large | OK (Using ModifyReservedInstances API and console) | OK (Using ModifyReservedInstances API and console) |
| Change Instance line, OS, tenancy, and payment method. V/d: from t2 -> to c4 | Impossible | OK |
| Benefit from AWS Discount | | Yes |
| Ability to resell on Marketplace | OK (After linking account with 1 US bank) | No |

Thus, compared to Savings Plan, Reserved Instance has more advantages that are
- You can buy 1 short term RIs on Marketplace this is not possible with Saving Plan.

- You can discount with RDS like EC2 (but not applicable to Fargate)
- Big discount when you choose 3-year term and pay all in advance, up to 60%
- Purchased Reserved Instance can be sold on the marketplace.

{{% notice info %}}
Note :
. RI applies not only to EC2 but also to RDS.
. With Standard RI, the more you use the same Instance line, the easier it is to buy RI.
. Similar to Savings Plan, there are 3 payment methods:
**All Upfront**: pay in full -> this will save you the most
**Partial Upfront**: pay 1 part upfront. Discount will be less than All Upfront but more than No Upfront
**No Upfront**: no prepayment, but only commitment will pay after the end of the term. This form has at least 3 discounts

{{% /notice %}}

Compared to On Demand Instance, RI is really a good and simple way to help users save costs for virtual servers. All you need to do is just subscribe for 1 year (or 3 years) to get a discount on the cost.