# Hermes AI Agent Architecture Documentation

## 1. Project Overview

Hermes is an AI Agent framework developed to support Business Excellence Center (BEC) activities by integrating Large Language Models (LLM), custom skills, knowledge management, and communication platforms.

The objective is to create an AI assistant that can be accessed by multiple users with consistent knowledge and capabilities.

---

# 2. Current Architecture (AS-IS)

## Current Flow

User
↓
Discord
↓
Hermes Agent (Local PC)
↓
Skill Library
↓
LLM Provider
↓
Response


## Current Deployment

- Hermes runs on local computer
- Discord acts as user interface
- Skills are stored locally
- Access depends on the machine running Hermes

---

# 3. Main Components

## Hermes Agent

Function:
- Receive user requests
- Execute skills
- Manage conversations


## Skills

Function:
Provide specific capabilities.

Examples:
- Business Modeler
- Business Excellence Assessor
- Book Writer
- Corporate Action Intelligence


## LLM Provider

Function:
Provides AI reasoning capability.

Example:
- OpenRouter API
- Other LLM providers


## Discord Integration

Function:
Provides multi-user interaction channel.

---

# 4. Current Limitation

1. Hermes depends on local computer availability.
2. Knowledge and memory are not yet centralized.
3. Multiple users still depend on one running machine.
4. Deployment scalability is limited.

---

# 5. Target Architecture (TO-BE)

User
↓
Discord
↓
Cloud Server / VPS
↓
Hermes Agent
↓
Knowledge Base + Persistent Memory
↓
LLM Provider
↓
Response


Target:

- Shared access for multiple users
- Centralized company knowledge
- Consistent AI response
- Scalable deployment
