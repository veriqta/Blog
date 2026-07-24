  # **Part 4: Project 1 — Creating and Configuring the CloudFront Distribution**

Welcome back. Your website is live on S3, but it's only served from one AWS region. If someone in Tokyo visits your site, their request travels all the way to Virginia (or wherever your bucket is). CloudFront fixes this by copying your site to edge locations around the world. Let's build that now.

---

## **4.1 Create the CloudFront Distribution**

**Step 1:** Sign in to the AWS Console as your IAM user.

**Step 2:** In the top search bar, type: `CloudFront`
- Click on **"CloudFront"** under Services.

**Step 3:** You'll land on the CloudFront Distributions page. It might be empty. Click the orange button **"Create distribution"**

**Step 4:** The "Create distribution" page opens. This has many sections. We'll configure each one carefully.

---

### **Section: Origin**

The "origin" is where CloudFront gets your content from. In our case, it's the S3 bucket.

**Step 5:** Under "Origin domain", click inside the text box.
- A dropdown appears showing your S3 buckets.
- Select your bucket: `veriqta-static-website-YOURNAME-2026.s3.us-east-1.amazonaws.com`
  - (Note: The exact format may vary slightly based on your region — it will show your bucket's S3 website endpoint or REST API endpoint)

**Wait — Important Decision Point:**

AWS will offer you two ways to connect to S3:
1. **S3 bucket (using the S3 REST API endpoint)** — This is the default option that appears.
2. **S3 static website hosting endpoint** — This requires manual entry.

**Which one should you choose?**

For a static website, you want CloudFront to use your S3 **static website endpoint** (the one with `s3-website` in the URL). This ensures that:
- `index.html` is served automatically when someone visits the root URL
- Your custom error page (`error.html`) works correctly
- URL routing behaves like a real website

**Step 6:** Instead of selecting from the dropdown, type your S3 static website endpoint manually into the "Origin domain" box:
```
veriqta-static-website-YOURNAME-2026.s3-website-us-east-1.amazonaws.com
```

Replace `YOURNAME` with your actual bucket name identifier.

**Step 7:** For "Origin path", leave it blank.

**Step 8:** For "Name", AWS will auto-fill something like `veriqta-static-website-YOURNAME-2026.s3-website-us-east-1.amazonaws.com`. You can leave it or shorten it to something like `s3-website-origin`. This is just a label.

---

### **Section: Default cache behavior**

This controls how CloudFront caches and serves your content.

**Step 9:** "Path pattern" — Leave as `Default (*)` (this applies to all files)

**Step 10:** "Viewer protocol policy" — Select **"Redirect HTTP to HTTPS"**
- This means if someone types `http://`, CloudFront automatically redirects them to `https://` (secure).
- This is the modern standard for websites.

**Step 11:** "Allowed HTTP methods" — Leave as **"GET, HEAD"**
- These are read-only methods, which is all we need for a static site.

**Step 12:** "Field-level encryption config" — Leave as **"No"**

**Step 13:** "Cache key and origin requests" — Select **"Cache policy and origin request policy (recommended)"**

**Step 14:** Under "Cache policy", select **"Managed-CachingOptimized"** from the dropdown.
- This is AWS's optimized policy for static content. It caches files at edge locations for maximum performance.

**Step 15:** Under "Origin request policy", select **"Managed-CORS-S3Origin"** from the dropdown.
- This handles Cross-Origin Resource Sharing headers properly for S3 origins.

**Step 16:** "Response headers policy" — Select **"Managed-SimpleCORS"** from the dropdown.
- This adds appropriate CORS headers to responses.

**Step 17:** "Enable real-time logs" — Leave unchecked.

**Step 18:** "Compress objects automatically" — Check this box.
- This enables gzip/Brotli compression, making your files smaller and faster to load.

---

### **Section: Settings**

**Step 19:** "Price class" — Select **"Use only North America and Europe"**
- This is the most cost-effective option for learning. It caches content in North American and European edge locations.
- If you want global coverage, select "Use all edge locations (best performance)" but note this costs more.

**Step 20:** "AWS WAF web ACL" — Leave as **"None"**
- WAF is a web application firewall. We don't need it for this basic project.

**Step 21:** "Alternate domain name (CNAME)" — Leave blank for now.
- This is where you'd add a custom domain like `www.yourdomain.com`. We'll skip this for the learning phase.

**Step 22:** "Custom SSL certificate" — Leave as **"Default CloudFront certificate (*.cloudfront.net)"**
- CloudFront provides a free SSL certificate for its default domain. Your site will be accessible via HTTPS.

**Step 23:** "Supported HTTP versions" — Leave as **"HTTP/2, HTTP/1.1, HTTP/1.0"**

**Step 24:** "Default root object" — Type exactly: `index.html`
- This tells CloudFront to serve `index.html` when someone visits the root URL of your distribution.

**Step 25:** "Logging" — Leave as **"Off"** for now.
- You can enable this later to see access logs, but it adds cost and complexity.

**Step 26:** "IPv6" — Leave as **"On"** (checked)

---

### **Create the Distribution**

**Step 27:** Scroll to the bottom of the page. Click the orange button **"Create distribution"**

**What happens next:**
- CloudFront begins creating your distribution. This is NOT instant.
- You'll be redirected to the CloudFront Distributions list.
- Your new distribution appears with a **"Status"** column showing **"In Progress"**
- The **"Last modified"** column shows the current time.

**Step 28:** Wait for the status to change from "In Progress" to **"Deployed"**
- This typically takes **5 to 15 minutes**, sometimes longer.
- Do NOT proceed until it says "Deployed". CloudFront is copying your configuration to edge locations worldwide.

**While waiting, note these important details:**
- Click on your distribution ID (it's a random string like `E123ABC4DEF5GH`)
- On the distribution details page, look for **"Distribution domain name"**
- It looks like: `d1234abcd5ef6.cloudfront.net`
- **Copy this domain name and save it.** This is your CloudFront URL.

---

## **4.2 Configure CloudFront Settings (Review & Verify)**

While waiting for deployment, let's review what we configured and understand why.

**Step 1:** On your distribution's details page, click the **"Origins"** tab.

**Step 2:** You should see one origin listed:
- Origin domain: Your S3 static website endpoint
- ID: The name you gave it
- Protocol: HTTP (because S3 static website endpoints only support HTTP, but CloudFront adds HTTPS on the front)

**Step 3:** Click the **"Behaviors"** tab.

**Step 4:** You should see one behavior:
- Path pattern: `Default (*)`
- Viewer protocol policy: `Redirect HTTP to HTTPS`
- Cache policy: `Managed-CachingOptimized`
- Compress objects automatically: `Yes`

**Step 5:** Click the **"Error pages"** tab.

**Step 6:** We need to add custom error handling so that 404 errors show your custom error page.

**Step 7:** Click **"Create custom error response"**

**Step 8:** Configure the custom error:
- **HTTP error code:** Select `404: Not Found`
- **Customize error response:** Select `Yes`
- **Response page path:** Type: `/error.html`
- **HTTP response code:** Select `404: Not Found` (or you can select `200: OK` if you want the browser to show a "soft" 404, but 404 is more honest)
- Click **"Create custom error response"**

**What this does:** When CloudFront receives a 404 from S3 (page not found), it serves your `error.html` page instead of a generic CloudFront error.

---

## **4.3 Test the CDN**

Once your distribution status shows **"Deployed"**, it's time to test.

**Step 1:** Open a new browser tab.

**Step 2:** In the address bar, type your CloudFront domain name:
```
https://d1234abcd5ef6.cloudfront.net
```
(Replace with your actual distribution domain name)

**Step 3:** Press Enter.

**What you should see:**
- Your beautiful website loads
- The URL starts with `https://` (secure connection)
- The page looks identical to the S3 version
- The URL is your CloudFront domain, not the S3 endpoint

**Step 4:** Test the error page. Manually type a non-existent URL:
```
https://d1234abcd5ef6.cloudfront.net/this-page-does-not-exist
```
- You should see your custom "Oops! Page Not Found" page
- The "Go Back Home" link should work

**Step 5:** Test HTTPS redirection. Type the HTTP version:
```
http://d1234abcd5ef6.cloudfront.net
```
- It should automatically redirect to `https://`

**Step 6:** Test caching. Refresh the page a few times.
- The first load might take a moment (CloudFront is fetching from S3)
- Subsequent loads should be nearly instant (served from the edge cache)

---

## **4.4 Troubleshooting**

If something doesn't work, here's how to diagnose it:

**Problem: CloudFront shows "Access Denied" or 403 error**
- **Cause:** CloudFront can't access your S3 bucket.
- **Fix:** 
  1. Go back to S3 > Your bucket > Permissions
  2. Verify your bucket policy is correct (from Part 3)
  3. Verify "Block all public access" is turned OFF
  4. Verify your files have public-read access
  5. In CloudFront, go to your distribution and click "Invalidations" tab
  6. Click "Create invalidation", type `/*`, click "Create invalidation"
  7. Wait 2-3 minutes and test again

**Problem: CSS/styles not loading**
- **Cause:** CloudFront cached an old version or the CSS file isn't accessible.
- **Fix:**
  1. Check that `style.css` is in your S3 bucket
  2. Verify the file has public-read access
  3. Create an invalidation (`/*`) in CloudFront
  4. Wait and test again

**Problem: Custom error page not showing**
- **Cause:** The error page configuration wasn't saved or the path is wrong.
- **Fix:**
  1. Go to CloudFront > Your distribution > Error pages tab
  2. Verify the custom error response exists for 404
  3. Verify the response page path is exactly `/error.html`
  4. Check that `error.html` exists in your S3 bucket root

**Problem: Distribution stuck "In Progress" for over 30 minutes**
- **Cause:** This is rare but can happen.
- **Fix:** Wait a bit longer. If it's been over 45 minutes, contact AWS support or try creating a new distribution.

---

## **Part 4 Summary Checklist**

Before moving on, verify you have:
- [ ] Created a CloudFront distribution
- [ ] Set the origin to your S3 static website endpoint (NOT the REST API endpoint)
- [ ] Configured "Redirect HTTP to HTTPS"
- [ ] Set "Default root object" to `index.html`
- [ ] Enabled "Compress objects automatically"
- [ ] Added a custom error response for 404 → `/error.html`
- [ ] Waited for distribution status to show "Deployed"
- [ ] Copied and saved your CloudFront domain name
- [ ] Tested the CloudFront URL and saw your website load via HTTPS
- [ ] Tested a non-existent URL and saw the custom error page
- [ ] Confirmed HTTP redirects to HTTPS
