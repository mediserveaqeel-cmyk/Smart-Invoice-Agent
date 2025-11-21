AI Invoice Automation Agent – README

Owner: Muhammad Aqeel
Email: mediserveaqeel@gmail.com

📌 Overview

This project is an end-to-end AI-powered automated invoice processing system built using n8n.

It monitors a Google Drive folder, detects new invoice PDFs, extracts invoice data using AI, updates a Google Sheets database, and automatically sends email notifications with processed results.

🚀 How the System Works
1. Google Drive Trigger

Watches a specific Google Drive folder for new invoice uploads.

Workflow triggers on the fileCreated event.

2. Download Binary

Downloads the uploaded invoice file as binary for further processing.

3. Extract From File

Extracts text from the uploaded PDF using n8n’s Extract From File node.

4. AI Information Extractor

Uses AI with a structured schema to extract key invoice details:

Invoice Number

Client Name

Client Email

Client Address

Client Phone

Total Amount

Invoice Date

Due Date

5. Google Sheets – Update Database

Appends extracted invoice data into a Google Sheets database.

6. AI Agent (Gemini)

Generates a professional email subject and body using Google Gemini based on invoice details.

7. Gmail Node

Sends automated email notifications to the client or internal team.

🛠️ How to Run This Project

Open n8n (Cloud or Self-hosted).

Import the workflow JSON file:
/mnt/data/Invoice Workflow SBS.json

Add the required credentials:

Google Drive OAuth

Google Sheets OAuth

Gmail OAuth

Google Gemini API

Update:

folderIDs

sheetIDs
(if necessary)

Activate the workflow.

Upload a PDF invoice to the watched Google Drive folder — automation starts instantly.

📦 Nodes Used

Google Drive Trigger

Google Drive – Download Binary

Extract From File

Information Extractor (LangChain)

Google Gemini Chat Model

Google Sheets (Append)

AI Agent (LangChain)

Gmail Node