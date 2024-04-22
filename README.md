![Picture1](https://github.com/Sandhyagito/Deploy-static-website-on-S3-bucket-and-configure-CloudFront-distribution/assets/151674108/549e2658-818b-4790-9b1f-fcb312fbdfc4)# Deploy-static-website-on-S3-bucket-and-configure-CloudFront-distribution
This repository contains the implementation of a secure, resilient, and globally accessible hosting solution for a static web page using AWS services. It leverages Amazon S3 for hosting, AWS WAF for firewall protection, and Amazon CloudFront for content distribution, geographical restrictions, and low latency access.

**Case Study Problem Statement:**

**An organization requires a solution for hosting a static web page that ensures firewall protection, failover capabilities, geographical restrictions, and low latency access.  
The current infrastructure lacks the necessary security measures, redundancy, and global accessibility, leading to potential security breaches, downtime, and slow website performance. 
To address these concerns, the organization needs a comprehensive hosting solution that can provide robust firewall protection, automatic failover mechanisms, the ability to enforce geographical restrictions for access and ensure low latency access to the web page for users worldwide.**


To address the challenges outlined in the problem statement, the following AWS services can be used to create a secure, resilient, and globally accessible hosting solution for a static web page:

**Amazon S3**:Hosts the static content of the web page and provides high durability and availability

**AWS WAF (Web Application Firewall)**: To protect the web page from common web exploits. Protects against common web attacks by controlling incoming and outgoing traffic

**Amazon CloudFront:** To distribute the content globally, ensuring low latency and implementing geographical restrictions.A content delivery network (CDN) that caches content at edge locations, ensuring low latency access globally.

**The key benefits of using Amazon S3, Amazon CloudFront, and AWS WAF for hosting a static web page include:**

**Enhanced Security:** AWS WAF provides robust protection against web exploits and attacks, ensuring the integrity and confidentiality of the web page.

**Improved Performance:** CloudFront’s global content delivery network ensures low latency and high transfer speeds for users around the world.

**Increased Reliability:** Amazon S3 offers high durability and availability for stored content, reducing the risk of data loss.
Cost savings are realized through:

**Pay-as-you-go Pricing:** You only pay for the services you use, without upfront costs, which can lead to significant savings.
Reduced Bandwidth Costs: CloudFront’s data transfer efficiency can lower overall bandwidth costs.
No Need for Physical Infrastructure: Eliminating the need to maintain physical servers reduces operational expenses.


**Task 1 - Creating S3 buckets**


Created 2 buckets in 2 different regions

Capstones3ytask1 - Primary bucket in US East N.Virginia

![Picture1](https://github.com/Sandhyagito/Deploy-static-website-on-S3-bucket-and-configure-CloudFront-distribution/assets/151674108/33ec3eea-34b8-4321-9ff3-eb4e0d313c3a)

Capstones3ytask2  -Secondary bucket in US East Ohio



4. Created an index.html page for the static website and uploaded the same file in 2 buckets


Uploaded index.html in both the storage buckets




Task -2: Creating a Cloud Front distribution

Create distribution



2. Choose primary for the origin domain



3. In Origin access, Select OAI option and create new OAI, Then select Yes, update bucket
policy.


4. Select redirect HTTP and HTTPS

5. Change Cache policy to Caching disabled


6. DO not enable WAF and leave the remaining by default, save.





Task 3 - Configuring CloudFront for failover
Create Origin


Select Secondary Bucket, select OAI, create OAI and yes, update the policy

Leave rest as default and create Origin

Create Origin Group
Capstones3origingroup - Origin Group name


Edit the default behavior, choose the origin group name and save



Task 4: Testing Failover

Go to Distribution, copy the Domain name




2. Paste domain name in browser and add /index.html in front of domain name.
You will observe website




Deleted index file in primary bucket

Try accessing the website again and see the results


Task - 5: Adding WAF to CloudFront

1. In your distribution -> go to general tab -> In settings click Edit.


2. Enable WAF then Save changes.

Task 6: Implementing Geo restriction
1. In your distribution -> go to geographic restriction tab -> click Edit.

2. Select the countries which you have to allow or block -> Save changes. (In my case I have
blocked access from India)


3. Copy distribution domain name and try to access from blocked location (You will get 403
error message)


Task 7: Invalidating data in cache
Created invalidation




Task 8: Deleting resources:

Disable distribution


Deleted the distribution


Removed the buckets


Conclusion:
By using Amazon S3 for hosting, Amazon CloudFront for fast content delivery, and AWS WAF for security, the organization has overcome its previous challenges with a secure, reliable, and efficient web hosting solution.
