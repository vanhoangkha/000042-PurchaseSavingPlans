+++
title = "Savings Plans Recommendation"
date = 2020-04-18T00:38:32+07:00
weight = 2
chapter = false
pre = "<b>2. </b>"
+++

To help users save maximum costs when using the service, AWS provides recommendations called **Savings Plan Recommendations** based on your past use of the service.
You can use these recommendations to optimize your service commitment to reduce costs.
- Monthly On-Demand Spend: Estimated On-Demand Spend based on usage during the selected period. It includes payments for Savings Plans that are active at the time of calculation.
    This value represents the Basic Spend for a month of On-Demand usage, based on past service usage and current Savings Plan commitments.

- Estimated Monthly Spend: estimated spending based on commitments to use the service as suggested by Savings Plan. This value includes the recommended commits and any expected usage to keep the On-Demand Instance up and running which varies hour to hour during usage.
- Estimated Monthly Savings: net monthly savings based on usage during the selected period when you purchase the recommended Savings Plans.

To access the Savings Plan Recommendation,
- Log in to **AWS Management Console** and then open **AWS Cost Management console** at https://console.aws.amazon.com/cost-management/home

- In the left navigation bar, under **Savings Plan**, select **Recommendation**

![Saving Plans](/images/SP/001.png?featherlight=false&width=90pc)

The Recommendation Savings Plan table shows the details of the Savings Plan options. You can also view Savings Plan Recommmendation information through the AWS Cost Explorer API.


![Saving Plans](/images/SP/002.png?featherlight=false&width=90pc)


{{% notice info %}}
Note: The steps below are only done when you want to buy Savings Plan based on the System's Recommendations. To learn how to purchase a customized Savings Plan you can skip to Step 3.
{{% /notice %}}


#### Customize SP Recommendation
Custom information includes:
- **Savings Plan Type** – Savings Plan Type. You can choose either Compute or Amazon EC2 Instance.

- **Savings Plan term** – commitment term in years. Choose 1-year or 3-years.
- **Payment option** – payment options for Savings Plan. It can be All-Upfront, Partial upfront, or No upfront.
- **Based on the past** – the number of days in the past is used to calculate the savings proposal or not
- **Filter by** – choose to determine which member account can view Savings Plan packages.

Specifically, the steps to customize SP Recommmendation are as follows:
- Access the AWS Cost Management console at https://console.aws.amazon.com/cost-management/home

- In the left navigation bar, under **Savings Plans**, select **Recommendations**.
- In the **Savings Plan type** section, select **EC2 Instance** or **Compute**.
- Select the term in the **Savings Plan term** section.
- Select the payment type in the **Payment option** section.
- Enter the number of days in the **Based on the past** section to calculate the SP recommendation based on that
- (Only applicable to Management Accounts) Click the **Linked Accounts** tab, select the Account IDs you want that Account to see the SP offer.
- (Optional) To pay, click the check box next to the desired SP package, then select **Add Savings Plans to cart**.

#### Recommended Savings Plan review on Recommendations page
Some cases when accessing the Recommendations page do not show any recommendations for Savings Plan. That's for one of two reasons:
- Firstly: it may be because AWS is not currently calculating any available outputs for Savings Plan.

- Second: because the spending on using On-Demand service is too low, less than 0.1$/hour in the selected time period.

These recommendations are automatically calculated making it easy for you to need reminders to purchase optimal Savings Plans, and you can add the recommended Savings Plans for your Account directly to your cart.

To start paying for the Savings Plans recommended on the Recommendations page, take the following steps:
- Sign in to the AWS Management Console and access the AWS Cost Management console at https://console.aws.amazon.com/cost-management/home

- In the left navigation pane, under Savings Plans, select Recommendations.
- In the options section of **Recommendation**, select **Savings Plans type**, **Savings Plans term**, **Payment option**, and lookback period.
- In the **Recommended Savings Plan** table, click the check boxes next to the Savings Plans that you want to pay for.
- Select **Add selected Savings Plan(s) to cart**.
- To complete the payment, click **Cart** in the left corner.
- At the Cart page, review the order and then click **Submit order**.

#### Pay Savings Plan on Purchase Savings Plans page
To pay **Saving