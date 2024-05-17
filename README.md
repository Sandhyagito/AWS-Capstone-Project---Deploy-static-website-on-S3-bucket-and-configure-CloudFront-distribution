**Deploy-static-website-on-S3-bucket-and-configure-CloudFront-distribution**

This repository contains the implementation of a secure, resilient, and globally accessible hosting solution for a static web page using AWS services. It leverages Amazon S3 for hosting, AWS WAF for firewall protection, and Amazon CloudFront for content distribution, geographical restrictions, and low latency access.

**Objective:**
The project aims to host a static web page with robust security, failover capabilities, geographical restrictions, and low latency access. The existing infrastructure lacked these features, leading to potential security breaches, downtime, and slow performance.

**Solution:**
The solution involves using AWS services to create a secure, resilient, and globally accessible hosting setup:

**Amazon S3:** Hosts the static content with high durability and availability.
**AWS WAF**: Protects against web exploits and controls traffic.
**Amazon CloudFront**: Distributes content globally, ensuring low latency and implementing geographical restrictions.

**Benefits:**

**Enhanced Security:** AWS WAF protects against web attacks.
**Improved Performance:** CloudFront ensures low latency and high transfer speeds.
**Increased Reliability:** S3 provides high durability and availability.
**Cost Savings:** Pay-as-you-go pricing, reduced bandwidth costs, and no need for physical infrastructure.

**Implementation Steps:**

**Create S3 Buckets:**

Two buckets were created in different regions (US East N. Virginia and US East Ohio) to ensure redundancy.
The static website's index.html was uploaded to both buckets.

**Create CloudFront Distribution:**

Configured the distribution using the primary S3 bucket as the origin.
Enabled HTTP to HTTPS redirection and set cache policy to disabled.
Configure Failover:

Added the secondary bucket as an origin for failover.
Created an origin group for failover configuration.

**Test Failover:**

Tested website accessibility by deleting the index.html in the primary bucket and ensuring it loaded from the secondary bucket.

**Add WAF to CloudFront:**

Enabled WAF in the CloudFront distribution settings for enhanced security.
Implement Geo Restriction:

Configured geographical restrictions to block access from specific countries.

**Invalidate Cache:**

Created invalidation to clear cached data in CloudFront.

**Delete Resources:** < BEST PRACTICES>

Disabled and deleted the CloudFront distribution and S3 buckets to clean up resources.

**Conclusion**:
The project successfully deployed a static website with enhanced security, reliability, and performance using Amazon S3, CloudFront, and AWS WAF, addressing the organization’s initial infrastructure shortcomings.

**Wrapping Up**🎁
Marrying S3 with CloudFront is like bringing together Batman and Robin 🦸‍♂️🦸‍♂️ — individually powerful, but together, they’re unstoppable. With enhanced speed, security, and scalability, it’s a match made in the cloud.

![diagram-export-5-2-2024-5_52_53-PM](https://github.com/Sandhyagito/AWS-Project--Deploy-static-website-on-S3-bucket-and-configure-CloudFront-distribution/assets/151674108/4274c1be-2467-4439-aa0e-74ee96ad61b2)
