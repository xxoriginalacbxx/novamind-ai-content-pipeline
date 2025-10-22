# 🧪 NovaMind AI-Powered Marketing Content Pipeline

Fully automated marketing content system that generates, distributes, and optimizes blog posts and newsletters using AI.

## 🎯 Overview

This project demonstrates an end-to-end AI content automation pipeline for **NovaMind**, a fictional AI startup that helps creative agencies automate their workflows. The system:

- ✅ Generates blog posts and persona-specific newsletters using OpenAI GPT-4
- ✅ Distributes content to segmented audiences via Mailchimp
- ✅ Tracks campaign performance metrics automatically
- ✅ Provides AI-powered weekly analytics with actionable insights
- ✅ Learns from past performance to optimize future content
- ✅ Automatically categorizes and segments new subscribers


## 🏗️ System Architecture

┌─────────────────────────────────────────────────────────────┐
│                    CONTENT LIFECYCLE                         │
└─────────────────────────────────────────────────────────────┘

Blog Topics (Google Sheets)
↓
[Scenario 1] Content Generation
↓
Mailchimp Distribution (3 personas)
↓
[Scenario 2] Performance Tracking (24hrs later)
↓
[Scenario 3] Weekly AI Analysis
↓
Optimization Insights → Feed back to Scenario 1

[Scenario 4] New Subscriber Management (ongoing)

## 🛠️ Tech Stack

- **Automation Platform**: Make.com
- **AI Content Generation**: OpenAI GPT-4 Turbo
- **Email Distribution**: Mailchimp
- **Data Storage**: Make.com Data Stores + Google Sheets
- **Form Collection**: Google Forms
- **Scheduling**: Make.com built-in scheduler

## 📊 Four Automated Scenarios

### Scenario 1: AI Content Generation & Distribution
**Trigger**: Scheduled (weekly) or manual  
**Purpose**: Creates blog posts and sends persona-specific newsletters

**Flow**:

Google Sheets (grab topics)
↓
Data Store (learn from past analysis insights)
↓
Array Aggregator (compile learnings)
↓
ChatGPT (generate blog post with context from past performance)
↓
Parse JSON
↓
Router → 3 branches:
├─ ChatGPT (Founders newsletter)
├─ ChatGPT (Creatives newsletter)
└─ ChatGPT (Operations newsletter)
↓
Mailchimp (create + send 3 campaigns)
↓
Tools (get campaign variables)
↓
Data Store (store campaign metadata)
↓
Google Sheets (update row with campaign IDs)

**Key Features**:
- Pulls insights from previous week's analysis
- Generates contextually-aware content based on what performed well
- Creates personalized newsletters for each audience segment
- Stores complete campaign data for tracking

---

### Scenario 2: Performance Tracking
**Trigger**: Scheduled (daily at 9 AM)  
**Purpose**: Collects campaign metrics 24 hours after send

**Flow**:

Google Sheets (pull campaign IDs)
↓
Router → 3 branches (one per persona):
├─ Mailchimp (get Founders report)
│      ↓
│  Data Store (store Founders metrics)
│
├─ Mailchimp (get Creatives report)
│      ↓
│  Data Store (store Creatives metrics)
│
└─ Mailchimp (get Operations report)
↓
Data Store (store Operations metrics)
↓
Google Sheets (mark as analyzed)

**Metrics Collected**:
- Open rate
- Click rate
- Unsubscribe rate
- Bounce rate
- Total opens/clicks
- Campaign send date

---

### Scenario 3: Weekly AI Analytics & Insights
**Trigger**: Scheduled (weekly, Monday 9 AM)  
**Purpose**: Analyzes performance and provides optimization recommendations

**Flow**:

### Scenario 3: Weekly AI Analytics & Insights
**Trigger**: Scheduled (weekly, Monday 9 AM)  
**Purpose**: Analyzes performance and provides optimization recommendations

**Flow**:
Data Store (pull all performance metrics)
↓
Array Aggregator (combine all data)
↓
ChatGPT (analyze performance, generate insights)
↓
Parse JSON
↓
Router → 2 branches:
├─ Data Store (store insights for future content generation)
└─ Google Sheets (log suggestions)
↓
Email (send weekly summary to team@novamind.ai)

**Analysis Output**:
- Executive summary of performance
- Persona-specific insights (what works, what doesn't)
- Recommended topics for next blog posts
- Actionable optimization strategies

**Email Report Includes**:
- Summary of weekly performance
- Best/worst performing personas
- Specific content recommendations
- Next topic suggestions based on data

---

### Scenario 4: New Subscriber Management
**Trigger**: Google Form submission (new email signup)  
**Purpose**: Automatically categorizes and segments new subscribers

**Flow**:

Google Form (new response: email + occupation)
↓
ChatGPT (categorize occupation → founder/creative/operations/none)
↓
Parse JSON
↓
Router (filter out "none" category)
↓
Mailchimp (add subscriber with appropriate persona tag)

**AI Categorization**:
- **Founders**: CEOs, Co-founders, Owners, Managing Directors, Presidents
- **Creatives**: Designers, Art Directors, Content Creators, UX/UI, Copywriters
- **Operations**: Ops Managers, Project Managers, COOs, IT Managers
- **None**: Students, Unemployed, unclear occupations (not added to lists)

---

## 👥 Three Audience Personas

Content is customized for distinct audience segments:

| Persona | Focus Areas | Content Angle | Example Subject Line |
|---------|-------------|---------------|---------------------|
| **Founders/Decision-Makers** | ROI, growth, efficiency, competitive advantage | Business metrics, case studies, strategic value | "47% Cost Reduction: AI ROI Calculator" |
| **Creative Professionals** | Inspiration, time-saving, creative freedom | Visual examples, storytelling, tool showcases | "AI Tools That Gave Me My Weekends Back" |
| **Operations Managers** | Workflows, integrations, reliability, technical implementation | Step-by-step guides, technical docs, process optimization | "Complete Integration Guide: Zapier + Notion + ChatGPT" |

---

## 🗄️ Data Architecture

### Google Sheets Structure
Single sheet: **"NovaMind Content System"**

| Column | Purpose |
|--------|---------|
| A - Blog Concept | Topic for next blog post |
| B - Approve Concept? | Yes/No approval status |
| C - Campaign Created? | Yes/No tracking |
| D - Founders ID | Mailchimp campaign ID |
| E - Creatives ID | Mailchimp campaign ID |
| F - OPs ID | Mailchimp campaign ID |
| G - Metrics Analyzed? | Yes/No tracking |

### Make.com Data Stores

**1. campaign_metadata**
```json
{
  "campaign_id_founders": "abc123",
  "campaign_id_creatives": "def456",
  "campaign_id_operations": "ghi789",
  "blog_topic": "AI in creative automation",
  "blog_headline": "How AI Transforms Creative Workflows",
  "blog_content": {...},
  "newsletter_content": {
    "founders": {...},
    "creatives": {...},
    "operations": {...}
  },
  "send_date": "2025-01-21T10:00:00Z",
  "status": "sent"
}

2. performance_metrics

{
  "campaign_id": "abc123",
  "persona": "founders",
  "blog_topic": "AI in creative automation",
  "subject_line": "Boost ROI with AI Automation",
  "send_date": "2025-01-21T10:00:00Z",
  "checked_date": "2025-01-22T09:00:00Z",
  "emails_sent": 150,
  "open_rate": 42.3,
  "click_rate": 11.2,
  "unsubscribe_rate": 0.3
}

3. optimization_insights

{
  "analysis_date": "2025-01-21T09:00:00Z",
  "summary": "Creatives showed strongest engagement...",
  "founders_insight": "ROI-focused content performs best...",
  "creatives_insight": "Visual content drives highest engagement...",
  "operations_insight": "Technical guides underperforming...",
  "next_topic": "Write '5 AI Design Tools' targeting Creatives..."
}

novamind-ai-content-pipeline/
│
├── README.md                          # This file
├── scenarios/                         # Make.com blueprints
│   ├── scenario-1-content-generation.json
│   ├── scenario-2-performance-tracking.json
│   ├── scenario-3-ai-analytics.json
│   └── scenario-4-subscriber-management.json
│
├── prompts/                          # All ChatGPT prompts
│   ├── blog-generation-prompt.txt
│   ├── newsletter-founders-prompt.txt
│   ├── newsletter-creatives-prompt.txt
│   ├── newsletter-operations-prompt.txt
│   ├── analytics-prompt.txt
│   └── occupation-categorization-prompt.txt
│
├── data-structures/                  # Data store schemas
│   ├── campaign_metadata.json
│   ├── performance_metrics.json
│   └── optimization_insights.json
│
├── templates/                        # Google Sheets template
│   └── content-system-template.xlsx
│
└── documentation/                    # Detailed guides
    ├── SETUP.md
    ├── ARCHITECTURE.md
    ├── DATA_FLOW.md
    └── images/

