
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

<h1>What Is an Edge Location?</h1>

![image alt](https://github.com/nikiimisal/S3-CLI-IAm/blob/main/cloudfront_location_edge.png?raw=true)

• An Edge Location (also called a Point of Presence or PoP) is a geographically distributed caching data center that AWS CloudFront uses to serve content closer to users. These locations are not the same as AWS Regions or Availability Zones—they exist to reduce latency by placing static and dynamic content nearer to viewers

• They cache copies of your content (e.g., images, CSS, HTML, videos), enabling faster delivery.

<h1>Uses & Benefits of Edge Locations</h1>

<h3>1. Low latency delivery</h3>

Requests from users go to the nearest edge location, reducing round-trip times and improving load speeds

<h3>2. Reduced origin load & cost</h3>

Serving cached content from the edge lessens the number of requests hitting your origin server, which can lower bandwidth and compute costs.

<h3>3. Reliability and resiliency</h3>

With content distributed across multiple edge locations, your application remains highly available even if one PoP fails.

<h3>4. Advanced processing capabilities</h3>

Edge Locations support features like Lambda@Edge and CloudFront Functions, enabling logic—such as custom headers, URL rewriting, or user-based personalization—to run at the edge.

<h3>5. SSL/TLS termination & acceleration</h3>

Edge servers handle encryption and request termination, improving performance and offloading work from origins .

>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.*


<h2>How to Set It Up CloudFront</h2>

<h3>Step‑by‑Step Overview:</h3>

  <h4>1. Prepare your S3 origin</h4>

 • Enable static website hosting (if needed) and upload your content.

 • Keep the bucket private and set up an OAI to grant CloudFront exclusive access.

 <h2>2. Create a CloudFront Distribution</h2>


 <h3>1. Access the S3 Console</h3>

•  Go to the Amazon S3 console.

• Verify whether the required buckets and objects are present.


<h3>2. Navigate to CloudFront and Create a Distribution</h3>

• Go to the AWS CloudFront service from the console.

• Start creating a new CloudFront distribution.

 -- Assign a Name: Provide an identifiable name for this distribution.

 -- Choose Distribution Type: Select the "Single website or application" option, assuming you're hosting a single site or app.

 -- Specify Domain Name (Optional): If you have a custom domain name, include it—although it's optional, adding it is ideal.

<h3>3. Configure the Origin (Data Source)</h3>

• Identify the source from which CloudFront will fetch data.

• Origin Type: Select "Amazon S3."

• Select the Bucket: Choose the specific S3 bucket from which the content should be delivered

<h3>4. Security Settings</h3>

• For practicing the setup only, do not enable any security protections like web application firewall (WAF), which usually involves additional costs.

<h3>5. Finalize and Create the Distribution</h3>

• Accept the basic default options displayed.

• Click Create Distribution to complete the setup.

>>• Set the origin domain to your S3 website endpoint (for static hosting) or the REST API endpoint if you want HTTPS to origin.
  • Configure Viewer Protocol Policy to redirect HTTP to HTTPS for secure delivery.
  • Define cache behaviors (default TTLs, compression, allowed methods such as GET/HEAD).
  • Add alternate domain names (CNAMEs) and attach an SSL certificate via ACM.








