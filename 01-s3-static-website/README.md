
# Hosting a Static Website with Amazon S3

## Overview

I completed this AWS project through NextWork's independent challenge mode. The aim was to understand how I could use Amazon S3 to host a website without needing to set up and manage a traditional web server.

I wanted to get more familiar with how S3 works, particularly how object storage, website hosting and permissions all come together.

## What I Did

- Created an Amazon S3 bucket to store the website files.
- Uploaded the `index.html` file along with the supporting images, CSS and other assets.
- Enabled static website hosting and configured `index.html` as the index document.
- Configured object permissions and ACLs to allow public access to the website files.
- Accessed the website through the S3 static website endpoint.

## How It Works

Amazon S3 stores the website files as objects inside a bucket.

When someone visits the S3 website endpoint, AWS serves the HTML page and its supporting assets directly from the bucket.

The important part was getting the permissions right. Without the correct access settings, visitors wouldn't be able to load the website.

This helped me understand the difference between simply storing files in S3 and actually making them accessible through a public website.

## What I Learned

The main thing I learned was how straightforward it is to host a static website using AWS without having to manage a server.

It also helped me understand the importance of bucket permissions and public access settings.

For a production website, I'd look at using CloudFront with a private S3 bucket, HTTPS and more restrictive access controls instead of relying on public object ACLs.

## Project Status

**Completed — AWS resources removed**

I successfully deployed the website using Amazon S3 static website hosting.

After finishing the project, I deleted the S3 bucket to avoid leaving unnecessary cloud resources running.

The website is no longer live, but I've uploaded the HTML and supporting website files to this repository as a reference to what I used during the project.

## Project Notes

This was a hands-on learning exercise completed independently through NextWork.

The website files were provided as part of the exercise, so this project demonstrates AWS static website hosting rather than website development.

I haven't included deployment screenshots, but the repository contains the website files used during the lab.
