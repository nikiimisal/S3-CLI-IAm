
<h1>AWS S3 CloudFront</h1>

![image alt](https://github.com/nikiimisal/S3-CLI-IAm/blob/main/thumbnail.png?raw=true)

<h2>What Is Amazon CloudFront (with S3)?</h2>

Amazon CloudFront is AWS’s globally distributed Content Delivery Network (CDN). 
It caches your content at edge locations around the world to serve it to users with minimal latency. When paired with an Amazon S3 bucket, CloudFront fetches content from S3 only when the cache is missing or stale.

<h2>Why Use CloudFront with S3?</h2>

• Faster global delivery: Content is served from the nearest edge location, significantly reducing latency.

• Origin offload & cost savings: Reduces load on your S3 bucket. There’s no data transfer fee from S3 to CloudFront—only costs for delivering content to end users.

• Enhanced security: Use Origin Access Identity (OAI) or Origin Access Control (OAC) to restrict S3 access so only CloudFront can fetch content.

• Access control features: Implement geo-restrictions, signed URLs or signed cookies, integrate with AWS WAF, and benefit from Shield DDoS protection.

• SSL/TLS support & custom domains: CloudFront enables HTTPS, custom domain names, and AWS-managed certificates (via ACM).

<h2>Common Use Cases</h2>

• Static website hosting with performance: Host your site on S3 and serve via CloudFront for low-latency access worldwide.

• Secured asset delivery: Use OAI to prevent direct access to S3, ensuring all traffic goes through CloudFront with SSL.

• Streaming and media: Efficiently stream video, audio, or large media with cached delivery.

• API or dynamic content acceleration: Speed up API endpoints by relying on CloudFront's global network.

• Geo-aware routing: Route users to the nearest region or even set up multi-origin failover (e.g., via Lambda@Edge).

>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.*


<h2>How to Set It Up</h2>

<h3>Step‑by‑Step Overview:</h3>

  <h4>1. Prepare your S3 origin</h4>

 • Enable static website hosting (if needed) and upload your content.

 • Keep the bucket private and set up an OAI to grant CloudFront exclusive access.

 <h3>2. Create a CloudFront Distribution</h3>

 • Set the origin domain to your S3 website endpoint (for static hosting) or the REST API endpoint if you want HTTPS to origin.

 • Configure Viewer Protocol Policy to redirect HTTP to HTTPS for secure delivery.

 • Define cache behaviors (default TTLs, compression, allowed methods such as GET/HEAD).

 • Add alternate domain names (CNAMEs) and attach an SSL certificate via ACM.








