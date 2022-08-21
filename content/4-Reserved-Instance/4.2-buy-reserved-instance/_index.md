+++
title = "Purchase Reserved Instance"
weight = 2
chapter = false
pre = "<b>4.2 </b>"
+++

#### How to purchase a Reserved Instance
To purchase Reserved Instance, visit the AWS homepage searching for Reserved Instance offerings, tweaking your search parameters until you find a match.
When you search for Reserved Instance, you'll see quotes about the cost of the respective results.
Before you confirm the purchase, review in detail the Reserved Instance that you intend to purchase and make sure that all parameters are correct.
Once payment is complete, you cannot cancel your purchase.

1. Select Platform for Instance
Amazon EC2 supports Reserved Instances running on Linux platforms as shown below:
- Linux/UNIX
- Linux with SQL Server Standard
- Linux with SQL Server Web
- Linux with SQL Server Enterprise
- SUSE Linux
- Red Hat Enterprise Linux

2. Place Payments on a Queue
By default, when you purchase Reserved Instances, payment will be made immediately.
However, you can set up this payment at a certain date and time in the future by placing it on the payment waiting list.
An order can be on the waiting list for up to three years. On the specified date and time, the order will be paid and the Reserved Instances pricing will apply.
You can view queued purchases in the Amazon EC2 console.
You can cancel a queued purchase at any time, as long as before the specified time. For details, you can see more at [Cancel a queued purchase](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-concepts-purchaseing.html#cancel-queued- purchase)

#### Proceed to purchase Reserved Instances of Standard type (Standard)
- Access **Amazon EC2 console** at https://console.aws.amazon.com/ec2/

- In the left navigation pane, select **Reserved Instances**, then continue to select **Purchase Reserved Instances**.
- For **Offering class**, select **Standard** to display all Reserved Instances of Standard type.
- If the specified reservation Instance is in a specific area, turn on **Only show offerings that reserve capacity** in the upper right corner of the payment screen. Once enabled, the Availability Zone field will appear.
- Adjust some other options, then click **Search**.
- For each Reserved Instance that you want to purchase, clearly enter the desired quantity and then click **Add to cart**.
- To purchase Standard Reserved Instance from **Reserved Instance Marketplace**, search for 3rd party in **Seller** column in search results. The Term column shows non-standard maturities.
- To view aggregate information for the type of Reserved Instances you have selected, click **View cart**.
- If the order payment time is **Now**, the payment will take place right after you click **Order all**.
  To put the Order on the waiting list, click Now and then select the date and time to pay.
- To complete payment for orders, click **Order all**.
- If at the time of ordering, there is an offer to purchase the same Instance but at a lower cost, AWS will suggest it for you to purchase at a lower cost.
- Click **Close**.
- The status of the order will be listed in the **State** column. When the order is paid, the State will change from **Payment-pending** to **Active**. When Reserved Instance is Active, it is ready for use.

#### purchase Reserved Instances of Convertible type
- Access the Amazon EC2 console at https://console.aws.amazon.com/ec2/

- In the left navigation pane, select Reserved Instances, then continue to select **Purchase Reserved Instances**.
- For **Offering class**, select **Convertible** to display all Reserved Instances of type Convertible.
- If the specified reservation Instance is in a specific area, turn on **Only show offerings that reserve capacity** in the upper right corner of the payment screen. Once enabled, the Availability Zone field will appear.
- Adjust some other options, then click **Search**.
- For each Reserved Instance that you want to purchase, clearly enter the desired quantity and then click **Add to cart**.
- To view aggregate information for the type of Reserved Instances you have selected, click **View cart**.
- If the Order payment time is Now, the payment will take place right after you click Order all.
  To put the Order on the waiting list, click Now and then select the date and time to pay.
- To complete payment for orders, click **Order all**.
- If at the time of ordering, there is an offer to purchase the same Instance but at a lower cost, AWS will suggest it for you to purchase at a lower cost.
- Click **Close**.
- The status of the order will be listed in the **State** column. When the order is paid, the State will change from **Payment-pending** to **Active**. When Reserved Instance is Active, it is ready for use.

#### purchase from Reserved Instance Marketplace
You can purchase Reserved Instances from a third party who owns the Reserved Instance but they no longer need to use them.
The purchase process is quite similar to when you make an Instance purchase on AWS.

Some of the differences between purchaseing Reserved Instance on Reserved Instance Marketplace and purchaseing directly on AWS are:
- **Term** – Reserved Instances purchased from a third party will have a shorter remaining term than when purchased directly on AWS. The term for a Reserved Instance when purchased on AWS is between 1 and 3 years.

- **Upfront price** – Third-party Reserved Instances may be sold with a different prepayment requirement than when purchased directly on AWS. Remaining usage or recurring costs remain the same as when purchasing a Reserved Instance directly from AWS.
- **Types of Reserved Instances** – Amazon EC2 Standard Reserved Instances can only be purchased on the Reserved Instance Marketplace. All other types such as Convertible Reserved Instances, Amazon RDS, and Amazon ElastiCache Reserved Instances are not available on this platform.

#### Check Reserved Instances

- Access the Amazon EC2 console at https://console.aws.amazon.com/ec2/

- In the left navigation pane, select **Reserved Instances**.
- Information about the payment waiting list, active RIs, and expired RIs will be listed here. The **State** column shows the status of the RIs.

### Cancel the order in the payment waiting list
An order can be on a payment waiting list for up to 3 years. So you can cancel the order at any time, as long as the order has not reached the time of activation.
To cancel do the following:
- Access the Amazon EC2 console at https://console.aws.amazon.com/ec2/

- In the left navigation pane, click **Reserved Instances**.
- Select one or more Reserved Instances.
- Click **Actions**, then select **Delete queued Reserved Instances**.
- When a message pops up asking for Confirm, press **Delete**, then **Close**.