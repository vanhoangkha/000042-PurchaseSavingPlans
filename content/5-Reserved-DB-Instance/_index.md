+++
title = "Reserved DB Instances"
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

Using reserved DB instances, you can reserve one or three years in advance. Reserved DB instances offer the benefit of a substantial discount compared to using On-Demand DB.
Depending on the version and each region, the discount for reserved DBs is different.

In general, the workflow with reserved DB instances includes the following steps: first get information about available reserved DB instances, then make a purchase of the selected reserved DB instance, and finally finally get information about currently available reserved DB instances. run.

### Reserved DB instances overview
When you buy reserved DB instances, you will receive a discount corresponding to the type of DB instance and the duration of that instance type. To use reserved DB instances, we actually create an Instance like creating an On-Demand DB Instance.
However, note that when creating a DB Instance, you must set the correct configurations with the purchased configuration Reserved DB Instance. If there is a difference in DB Instance creation, you will be charged immediately for On-Demand DB Instance creation.

Similar to Savings Plan or RI, payment for Reserved DB Instance is also divided into 3 types:
- **All Upfront**: pay in full -> this will save you the most

- **Partial Upfront**: pay 1 part upfront. Discount will be less than All Upfront but more than No Upfront
- **No Upfront**: no prepayment but only commitment will pay after the end of the term. This form has at least 3 discounts

When purchasing a Reserved DB Instance, one thing you need to specify is the Reserved DB Instance's Instance class. By purchasing reserved DB Instance, this information cannot be changed.
The size of the Instance may change as the Instance auto-scales, or the Instance may be moved to another region, even if the Instance is configured with Multi-AZ or Single-AZ, pricing for the Reserved DB Instance is not change.
However, if you change the Instance Class, for example from db.m4.large to db.m5.large, the billing will not be applied at all. The Instance price is now calculated according to the On-Demand DB Instance price.

The types of RDS DB engines that are available with the Reserved DB Instance are:
- MariaDB
- MySQL
- Oracle, Bring Your Own License
- PostgreSQL

A commitment to use will have a term of one to three years. During this time, you will not be able to cancel the DB Instance, you can only delete the DB Instance.
Deleting it is the same as for other DB Instances.
Once you have deleted the DB Instance that has been priced at the Reserved DB Instance, you can completely create another DB Instance and still keep the same discounted pricing as the original commitment.
However, make sure the new DB Instance still belongs to the same Instance Class, and to the same DB engine.

### Working with reserved DB instances

To make available Reserved DB Instance purchase, follow these steps:
- Go to the AWS Management Console and open the Amazon RDS console at https://console.aws.amazon.com/rds/

- In the right navigation pane, select **Reserved instances**.
- Continue to select **Purchase Reserved DB Instance**.
- Section **Product description**, Select **DB engine** and **licensing type**.
- For **DB instance class**, select the DB instance class you want to use.
- For **Multi-AZ** deployment option, check if you want to deploy this configuration.
- With **Term**, choose how long you want to use DB instance reserved.
- With **Offering type**, select the payment type. Soon you will see the cost information corresponding to the payment method you have selected.
- Click on **Continue**. A **Purchase Reserved DB Instance** dialog box appears, with the aggregate configuration of the reserved DB instance you selected along with the payment due.
- On the **Confirmation** page, review the last reserved DB instance. If the information is correct, click **Purchase** to purchase a reserved DB instance.
- Otherwise, click **Back** to edit the configuration of the reserved DB instance to be purchased.

Congratulations on learning about Savings Plan, Reserved Instance and Reserved DB Instance. Hope this workshop brings useful information to you.