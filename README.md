YouTube AI Content Repurposer (Agentic Workflow)
Executive Summary
This n8n-powered AI agent automates the high-friction task of manual content repurposing. It transforms a single YouTube video URL into professional, platform-specific social media drafts (LinkedIn and Twitter/X) in seconds, utilizing a Human-in-the-loop approval system to ensure 100% content quality before distribution.
________________________________________
Key Features

•	Multi-Platform Summarization: Generates a structured LinkedIn post and a punchy Twitter thread simultaneously using Gemini 2.5 Flash.

•	Metadata Extraction: Automatically fetches video titles, descriptions, and high-resolution thumbnails via the YouTube API.

•	Human-in-the-Loop Approval: Content is staged in a Google Sheet for review; publication is only triggered when a human sets the status to "Approved".

•	Rich Media Delivery: Delivers a fully formatted "Media Card" to Discord, including the video thumbnail and summary, for final distribution.

________________________________________
Technologies Used

•	n8n: Visual workflow automation and orchestration.

•	Google Gemini 2.5 Flash: Advanced reasoning for content analysis and creative writing.

•	YouTube API (HTTP Request): For automated data extraction.

•	Google Sheets: As a low-code database and approval dashboard.

•	Discord Web hooks: For instant delivery of approved content.

•	JavaScript (Code Node): To parse AI responses and dynamically generate thumbnail URLs.
________________________________________
Project Architecture

The system is divided into two distinct logical segments:

1.	Intake & Generation:
   
o	Trigger: User submits a YouTube URL via a form.

o	Extraction: HTTP Request fetches video metadata.

o	Intelligence: Gemini analyzes data and generates a structured JSON object.

o	Storage: Data is appended to a Google Sheet with a "Pending" status.

2.	Review & Distribution:
   
o	Trigger: A Google Sheets trigger watches for "Status" updates.

o	Filter: An "If" node ensures only "Approved" rows proceed.

o	Distribution: Discord receives a high-quality Rich Embed card with the final copy and video thumbnail.
________________________________________
Business Value

•	Time Savings: Reduces manual writing time by approximately 90% per video.

•	Consistency: Maintains a professional brand voice across multiple social channels.

•	Safety: The approval gate prevents AI hallucinations or errors from reaching the public.

