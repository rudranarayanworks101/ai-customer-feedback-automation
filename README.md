# ai-customer-feedback-automation
AI-powered customer feedback classification and automated triage using n8n, Google Gemini, Airtable, Slack, and Gmail.
# 🤖 AI-Powered Customer Feedback Automation

An end-to-end AI automation workflow that analyzes free-form customer feedback, classifies it using Google Gemini, stores structured insights in Airtable, notifies the relevant team through Slack, and automatically sends a confirmation email to the customer.

## 🚀 Overview

Customers can submit feedback in their own words through a form. The workflow uses AI to understand the feedback rather than requiring customers to select a predefined category.

The AI extracts:

- Primary category
- Secondary categories
- Sentiment
- Priority
- Topic
- Summary
- Issues
- Feature requests
- AI confidence
- Human-review requirement

The structured result is then routed automatically through the workflow.

## 🏗️ Architecture

```text
Customer
   │
   ▼
Feedback Form
   │
   ▼
Google Gemini AI
   │
   ▼
Structured Feedback Analysis
   │
   ▼
Switch / Routing
   │
   ├──────────────┬──────────────┐
   ▼              ▼              ▼
Complaint       Praise      Feature Request
   │              │              │
   └──────────────┴──────────────┘
                  │
                  ▼
              Airtable
                  │
                  ▼
                Slack
                  │
                  ▼
           Confirmation Email
