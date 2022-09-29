## Many AWS Accounts
* Lots of organizations are following approach of having multiple AWS Accounts
* For example, separate AWS account for DEV, Staging, Production
* It brings quiet lot of benefits which includes security as well as costing

## What many startups do ?
A Startup has 3 AWS accounts which they use to separate their environment as part of good security best practice. At end of the month, they get 3 separate bill and they pay for each and every account individually

## Consolidated Billing
We need to link all our AWS accounts with the central paying account through AWS Organizations
 
## Benefits
There are a lot of benefits of consolidated billing: 
* One bill per linked AWS account
* It becomes quite easy to allocate costing and budgets
* Benefits of volume pricing discounts
* Benefits when using reserved instances as well

 
| <b><u>TB/month</u></b> | <b><u>$ per GB</u></b> |
| :---                   | :---         | 
| :small_orange_diamond: First 50TB/month | Standard Storage = $0.023 per GB |
| :small_orange_diamond: Next 450TB/month  |  Standard Storage = $0.022 per GB |
| :small_orange_diamond: First Over 500TB/month | Standard Storage = $0.021 per GB |


## Reserverd Instance Benefits
Paying Account -> Dev Account: Running 6 on demand instances 
                           -> Prod Account: Has 6 RI and running 3 instances
 
Total Bill: We will be billed for 6 RI and only 3 on-demand instances

## Important Pointers & Best Practices
* Paying account should be used for billing purpose only. Do no deploy resource there
* By default, we can have maximum of 20 linked accounts
* Even when linked, paying account is individual and does not have access on resources of the other accounts
