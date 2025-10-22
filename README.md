# 🧪 NovaMind AI-Powered Marketing Content Pipeline

Automated marketing content system that generates, distributes, and optimizes blog posts and newsletters using AI.

## 🎯 Overview

This project demonstrates an end-to-end AI content automation pipeline for **NovaMind**, a fictional AI startup. The system:

- ✅ Generates blog posts and persona-specific newsletters using OpenAI GPT-4
- ✅ Distributes content to segmented audiences via Mailchimp
- ✅ Tracks campaign performance automatically
- ✅ Provides AI-powered analytics and optimization insights

## 🏗️ Architecture

Content Generation → Distribution → Performance Tracking → AI Analysis
↓                  ↓                ↓                  ↓
OpenAI GPT-4      Mailchimp      Data Stores        Weekly Insights

## 🛠️ Tech Stack

- **Automation Platform**: Make.com
- **AI Content Generation**: OpenAI GPT-4 Turbo
- **CRM**: Mailchimp
- **Data Storage**: Make.com Data Stores + Google Sheets
- **Scheduling**: Make.com built-in scheduler

## 📊 Scenarios

### Scenario 1: Content Generation & Distribution
Generates blog posts and 3 persona-specific newsletters, then distributes via Mailchimp.

**Flow**: Schedule → Google Sheets → OpenAI → Mailchimp → Data Store

### Scenario 2: Performance Tracking
Collects campaign metrics from Mailchimp and stores in data stores.

**Flow**: Schedule → Data Store → Mailchimp Reports → Data Store

### Scenario 3: AI Analytics & Insights
Analyzes performance data and generates optimization recommendations.

**Flow**: Schedule → Data Store → OpenAI Analysis → Email Report

## 👥 Personas

Content is customized for three audience segments:

1. **Founders/Decision-Makers** - Focus: ROI, growth, efficiency
2. **Creative Professionals** - Focus: Inspiration, time-saving, creative freedom
3. **Operations Managers** - Focus: Workflows, integrations, reliability

## 📁 Repository Structure

├── scenarios/              # Make.com scenario blueprints (JSON)
├── prompts/               # ChatGPT prompts for content generation
├── data-structures/       # Data store schemas
├── documentation/         # Setup guides and architecture docs
└── README.md             # This file

## 🚀 Quick Start

1. Clone this repository
2. Import scenario JSON files into Make.com
3. Configure API keys (OpenAI, Mailchimp)
4. Set up data stores in Make.com
5. Run Scenario 1 to generate first campaign

Detailed setup instructions: [See documentation folder]

## 📈 Results & Insights

The system automatically:
- Generates personalized content for each persona
- Tracks open rates, click rates, and engagement
- Provides weekly AI-powered recommendations
- Suggests optimized topics for future content

## 🔑 Key Features

- **Fully Automated**: Runs on schedule with no manual intervention
- **AI-Powered**: Uses GPT-4 for content generation and analysis
- **Data-Driven**: Makes recommendations based on actual performance metrics
- **Scalable**: Easy to add new personas or content types

## 📝 Notes

This is a take-home assignment project demonstrating:
- AI/LLM integration
- Marketing automation workflows
- CRM integration
- Performance analytics
- System architecture design

---

**Created by**: Auston Baker
**Date**: January 2025
**Contact**: austonbaker@berkeley.edu
