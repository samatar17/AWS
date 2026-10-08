AWS Assignment 3 – Hosting a Website with S3, CloudFront and Route 53
Overview
I've completed my third AWS assignment as part of my DevOps learning journey with CoderCo.

In this assignment, I built and deployed a website using Amazon S3, CloudFront and Route 53. I also connected my own domain and secured the website using HTTPS.

Live website: https://aws.samatar.co.uk

What I Did
Created an Amazon S3 bucket to store my website files.
Uploaded index.html and error.html.
Created a CloudFront distribution.
Configured Route 53 to connect my custom domain.
Created an SSL/TLS certificate using AWS Certificate Manager.
Enabled HTTPS for secure access.
Updated my website and created a CloudFront invalidation to refresh the cached content.
Challenges I Faced and How I Fixed Them
1. Setting Up Route 53
I found the nameserver configuration confusing at first. I wasn't sure which addresses to copy or where to enter them.

I worked through the DNS setup carefully and continued until the domain configuration was in place.

2. SSL Certificate Problem
When I tried connecting my domain to CloudFront, AWS couldn't find a suitable SSL certificate.

I fixed this by creating a certificate using AWS Certificate Manager and selecting it for my CloudFront distribution.

3. Connecting My Domain
After configuring CloudFront, I still needed to connect my domain correctly.

I used Route 53 to set up DNS routing and received confirmation that the records had been updated successfully.

I then tested my website using my custom domain, and it loaded correctly.

4. Updating My Website
After my website was working, I updated the HTML file to reflect what I had achieved.

I uploaded the updated file to S3 and created a CloudFront invalidation to clear the cached version.

The invalidation completed successfully.

What I Learned
This assignment helped me understand how different AWS services work together.

I gained practical experience with:

Cloud storage and static website hosting
DNS configuration
Content delivery networks
SSL/TLS certificates and HTTPS
CloudFront caching and invalidations
I also learned the importance of troubleshooting problems rather than rushing through the steps.

Final Result
I successfully deployed my website and connected it to my custom domain.

Website: https://aws.samatar.co.uk

This was another useful hands-on assignment that helped me build my confidence with AWS.

I'm looking forward to continuing my DevOps learning and taking on more challenging projects.
