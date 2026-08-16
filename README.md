# AetherPost

> AI-powered social media automation that transforms Google Drive images into polished Instagram posts with intelligent content generation, duplicate protection, validation, automated publishing, and persistent post tracking.

---

## Overview

AetherPost is an end-to-end AI-powered Instagram content automation system built with n8n.

The system monitors a designated Google Drive folder for new content, identifies supported image files, downloads and prepares them, checks Supabase to determine whether an image has already been published, generates captions and hashtags using AI, validates the generated content, creates an Instagram media container, publishes the post automatically, and records the result in Supabase.

The workflow is designed to be repeatable and safe. Existing images are not repeatedly published, while PDFs and other unsupported files are automatically ignored.

The entire publishing pipeline is orchestrated through n8n, with Google Drive acting as the content source, Supabase handling storage and persistent logging, AI handling content generation, and the Instagram Graph API handling publication.

---

## What AetherPost Does

AetherPost automates the complete journey from a file being placed in Google Drive to a published Instagram post.

```text
Google Drive
      |
      v
Fetch Files
      |
      v
Split Files
      |
      v
Filter Images
      |
      +--------------------+
      |                    |
   Image                 Non-Image
      |                    |
      v                    v
Download              Skip Non-Image
      |
      v
Prepare Image
      |
      v
Check Duplicate
      |
      +--------------------+
      |                    |
   New Image            Duplicate
      |                    |
      v                    v
AI Content              Skip Duplicate
Generation
      |
      v
Validate AI Output
      |
      v
Create Instagram
Media Container
      |
      v
Publish to Instagram
      |
      v
Log Post in Supabase
