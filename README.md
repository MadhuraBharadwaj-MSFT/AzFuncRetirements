# Azure Functions Retirement Assistant Agent

A specialized AI assistant agent designed to help Azure Functions teams manage the end-to-end process of retiring Azure Functions features and runtime versions.

## Overview

The Functions Retirements Assistant Agent guides users through required steps, automates repetitive tasks, and ensures all compliance and communication requirements are met during feature retirements.

## Features

### 🚀 CPEX Retirement Process
- Guides users through the complete CPEX retirement workflow
- Automates intake submission and approval tracking
- Provides CSS guidance and escalation paths

### 📚 Documentation Management
- Identifies documentation impacted by retirements
- Generates migration guides and upgrade instructions
- Follows Microsoft documentation update policies

### 📊 Impact Analysis
- Executes Kusto queries to assess customer impact
- Identifies top impacted customer accounts
- Surfaces product errors and warnings related to retirements

### 📧 Customer Communication
- Drafts personalized email announcements
- Suggests outreach steps for high-impact customers
- Provides escalation templates for account teams

## Current Retirement Projects

### Node.js 20 Retirement (Active)
- **End Date:** April 30, 2026
- **Impact:** 200K+ function apps across 1000+ subscriptions
- **Critical Customer:** 203,643 apps in single subscription
- **Status:** Impact analysis complete, customer outreach in progress

## Project Structure

```
FuncRetirementsAgent/
├── .github/
│   └── chatmodes/
│       └── AzFuncRetirementAssistant.chatmode.md  # AI agent specification
├── RetirementSummary.md                           # Active retirement tracking
├── mcp.json                                      # MCP server configuration  
└── README.md                                     # This file
```

## Usage

### Starting a New Retirement
1. Reference the [CPEX retirement process documentation](https://eng.ms/docs/cloud-ai-platform/azure-core/azure-core-product/product-lifecycle-management-plm/service-lifecycle-and-actions-team/service-lifecycle-actions-team/cpex/media/how_to_retirements)
2. Collect: Feature name, retirement timeline, known impacted customers
3. Follow the agent's step-by-step guidance through the CPEX process

### Impact Analysis
The agent uses Kusto queries against the Azure Functions telemetry to:
- Identify total customer impact
- Find top 10 most affected subscriptions
- Generate customer contact lists for outreach

### Documentation Updates
Follow the **Doc Update Policy**:
- When docs mention retiring versions as prerequisites, update with latest version info
- No need to explicitly state the current version is retiring
- Focus on forward-looking guidance

## Requirements

- Access to Azure Data Explorer (Kusto)
- VS Code with Azure Data Explorer extension
- Access to internal Microsoft documentation systems
- CPEX process permissions

## Language Support Policy

All retirements follow the [Azure Functions Language Support Policy](https://learn.microsoft.com/en-us/azure/azure-functions/language-support-policy?pivots=programming-language-javascript)

## Contributing

This is an internal Microsoft project for Azure Functions retirement management. Contact the Azure Functions team for access and contribution guidelines.

## License

Internal Microsoft use only.
