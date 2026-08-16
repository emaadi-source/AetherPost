# AI Instagram Content Automation

> An AI-powered content pipeline that turns images stored in Google Drive into ready-to-publish Instagram posts automatically.

## Overview

AI Instagram Content Automation is an end-to-end workflow designed to remove the repetitive work involved in publishing social media content.

The system continuously checks a Google Drive folder, identifies valid image files, prepares them for Instagram, generates engaging captions and hashtags with AI, validates the generated content, publishes the image through the Instagram Graph API, and records the published file in Supabase.

The result is a fully automated content publishing pipeline with built-in filtering and duplicate protection.

## Workflow

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
     +---- Non-Image ----> Skip
     |
     v
Download Image
     |
     v
Prepare Image
     |
     v
Check Duplicate
     |
     +---- Already Posted ----> Skip
     |
     v
Generate & Validate AI Content
     |
     v
Create Instagram Media Container
     |
     v
Publish to Instagram
     |
     v
Log Post in Supabase
