# AWS Cloud Foundations Homework

## Task 1.3 - Budget Alert

### What triggers the alert email, and how long does it take?

The alert is triggered when AWS records that the actual spend has crossed the threshold configured for the budget. It is not triggered immediately when a resource is started or used, because AWS billing information is not updated in real time. The spend first has to appear in the billing data, and then AWS Budgets evaluates it against the threshold. Because of this delay, the email can arrive several hours after the cost was generated, often around 8-12 hours later and sometimes longer.

## Task 2.1 - Shared Responsibility Model

A company uses Amazon S3 to store private customer documents such as invoices. An employee misunderstands the Shared Responsibility Model and assumes that because AWS is secure, every file stored in S3 will automatically have the correct access settings. While configuring the bucket, the employee changes the permissions incorrectly and allows public read access to the files. As a result, someone outside the company could access confidential customer invoices if they obtained the object links. AWS itself was not compromised and the S3 service continued to work as designed. AWS is responsible for protecting the infrastructure that runs S3, while the customer is responsible for configuring access to the data stored there. AWS provides tools such as bucket policies, IAM permissions, and public access controls, but it cannot decide which company files should be public or private. In this case, the data exposure happened because of a customer-side configuration mistake.

## Task 2.2 - Capital Expense vs Operating Expense

A physical server is mainly a capital expense because its purchase price is known in advance. AWS is based on ongoing usage, so the operating cost can increase as more resources, storage, or traffic are consumed. A budget alert is useful because it warns when that variable spending goes beyond the expected level.

## Task 2.3 - Regions and Availability Zones

AWS divides a Region into multiple Availability Zones so that a problem in one physical location does not necessarily affect the whole Region. By spreading an application across several Availability Zones, an architect can reduce dependence on a single failure point and improve availability and fault tolerance. If one Availability Zone becomes unavailable, resources in another zone can continue serving the application.

## Task 2.4 - IAM Users vs Roles

IAM users can have long-term credentials that remain valid until they are rotated or revoked. Roles are preferred because they provide temporary credentials that expire automatically after a limited period. If a long-term access key is leaked through source code, logs, or a public repository, an attacker may continue using it until someone manually disables it. Temporary role credentials reduce this risk because they have a limited lifetime and do not require permanent secrets to be stored in the application.
