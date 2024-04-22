**Deploy-static-website-on-S3-bucket-and-configure-CloudFront-distribution**

This repository contains the implementation of a secure, resilient, and globally accessible hosting solution for a static web page using AWS services. It leverages Amazon S3 for hosting, AWS WAF for firewall protection, and Amazon CloudFront for content distribution, geographical restrictions, and low latency access.

**Case Study Problem Statement:**

**An organization requires a solution for hosting a static web page that ensures firewall protection, failover capabilities, geographical restrictions, and low latency access.  
The current infrastructure lacks the necessary security measures, redundancy, and global accessibility, leading to potential security breaches, downtime, and slow website performance. 
To address these concerns, the organization needs a comprehensive hosting solution that can provide robust firewall protection, automatic failover mechanisms, the ability to enforce geographical restrictions for access and ensure low latency access to the web page for users worldwide.**


To address the challenges outlined in the problem statement, the following AWS services can be used to create a secure, resilient, and globally accessible hosting solution for a static web page:

**Why Combine S3 and CloudFront**?

**Scalability:* S3’s virtually unlimited storage meets CloudFront’s robust CDN network.
**Performance:* With CloudFront’s global edge locations, content is served from the nearest location, reducing latency.
**Security:* Control access, integrate with AWS WAF, and deliver content over HTTPS.

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


