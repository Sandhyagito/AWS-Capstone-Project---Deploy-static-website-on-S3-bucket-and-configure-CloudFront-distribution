**Deploy-static-website-on-S3-bucket-and-configure-CloudFront-distribution**

This repository contains the implementation of a secure, resilient, and globally accessible hosting solution for a static web page using AWS services. It leverages Amazon S3 for hosting, AWS WAF for firewall protection, and Amazon CloudFront for content distribution, geographical restrictions, and low latency access.

**Objective:**
**The project aims to host a static web page with robust security, failover capabilities, geographical restrictions, and low latency access. The existing infrastructure lacked these features, leading to potential security breaches, downtime, and slow performance.**

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

**Combining Amazon S3 and Amazon CloudFront provides several benefits that enhance the performance, security, and reliability of hosting a static website. Here are the key reasons for using S3 and CloudFront together:**

**1. Performance and Low Latency**
Content Delivery Network (CDN): CloudFront is a CDN that caches your content at multiple edge locations around the world. This means that user requests are served from the closest edge location, reducing latency and improving load times.
High Transfer Speeds: By delivering content through CloudFront, users experience faster download speeds, which is critical for improving user experience and reducing bounce rates.

**2. Scalability and Availability**
High Durability and Availability of S3: Amazon S3 is designed to provide 99.999999999% (11 nines) of durability and 99.99% availability of objects over a given year. This ensures that your static website content is stored reliably.
Automatic Scaling: Both S3 and CloudFront automatically scale to handle varying traffic loads without manual intervention, ensuring your site remains accessible during traffic spikes.

**3. Security Enhancements**
AWS WAF Integration: CloudFront integrates with AWS WAF (Web Application Firewall) to protect against common web attacks such as SQL injection and cross-site scripting. This adds a layer of security to your static site.
DDoS Protection: CloudFront offers built-in DDoS protection via AWS Shield, which helps protect against large-scale attacks.

**4. Geographical Restrictions**
Geo-blocking: CloudFront allows you to restrict access to your content based on geographic locations. This is useful for compliance with regional regulations or targeting specific markets.

**5. Cost Efficiency**
Reduced Data Transfer Costs: Delivering content through CloudFront can reduce the overall cost of data transfer from S3 to your users, as CloudFront edge locations cache your content and reduce the load on your S3 bucket.
Pay-as-You-Go Pricing: Both S3 and CloudFront offer pay-as-you-go pricing, allowing you to pay only for the storage and data transfer you actually use, which can lead to significant cost savings compared to traditional hosting solutions.

**6. Reliability and Redundancy**
Failover Capabilities: CloudFront can be configured with multiple origins and origin groups to provide automatic failover. If your primary S3 bucket becomes unavailable, CloudFront can switch to a secondary bucket, ensuring continuous availability of your site.

**7. Ease of Management**
Simplified Content Management: Using S3 to store your static content makes it easy to manage and update your website. Changes to your content are automatically reflected in CloudFront’s edge caches after invalidation.

**Integration with Other AWS Services:** S3 and CloudFront integrate seamlessly with other AWS services, providing a comprehensive and cohesive solution for hosting and delivering static websites.

By combining Amazon S3 and CloudFront, you create a robust, secure, and performant infrastructure for your static website that can handle global traffic efficiently and cost-effectively.
