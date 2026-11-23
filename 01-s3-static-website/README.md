# Hosting a Static Website with Amazon S3
Overview
I completed this AWS project through NextWork's independent challenge mode. The aim was to understand how I could use Amazon S3 to host a basic website without needing to set up and manage a web server.

It was a good introduction to S3, particularly how object storage, website hosting and permissions work together.
What I did
- Created an S3 bucket to store the website files.
- Uploaded the index.html page and its supporting images and assets.
- Enabled static website hosting and set index.html as the index document.
- Worked with object permissions and ACLs to make the website files publicly readable.
- Used the S3 website endpoint to access the site.
How it works
The website files are stored as objects in an S3 bucket. When someone opens the bucket's website endpoint, S3 serves the HTML page and its assets. The files need the correct read permissions or visitors will get an access-denied response.

This helped me understand the difference between storing a file in S3 and actually making that file accessible to the public.
What I learned
The main takeaway was how straightforward it is to host a static site using AWS, but also how important access settings are. Making a bucket or its objects public is a deliberate security decision, not something I would do for general-purpose storage.

For a production website, I'd look at CloudFront with a private S3 bucket, HTTPS and tighter access controls rather than relying on a publicly accessible S3 website endpoint and object ACLs.
Project notes
This was a hands-on learning exercise completed independently using the NextWork S3 project. The site uses the project-provided website assets; it isn't a custom web application. I haven't included a live endpoint or screenshots in this repository.
