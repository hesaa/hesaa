---
title: "Taskflow — AI Task Management"
date: "Jul 2026"
tags: ["TypeScript", "Next.js", "Express.js", "AI"]
excerpt: "Full-stack AI-powered task management platform with natural language command processing and kanban board."
description: "AI-powered task management platform with natural language command processing."
url: https://taskflow.hesaa.xyz
---

Taskflow is a full-stack task management platform with natural language AI command processing. I built the entire system from a pnpm monorepo with Turborepo, handling both the API and web application.

## What I Did

- Architected a pnpm monorepo with Turborepo for API, web app, and shared packages
- Built an Express API with Prisma ORM, PostgreSQL, and Redis for real-time features
- Implemented AI command processing using natural language to create, update, and delete tasks
- Designed a drag-and-drop kanban board with Next.js 16 and shadcn/ui
- Added role-based access control with admin and user roles
- Implemented audit logging with request/response payloads for compliance

## Tech Stack

- Next.js 16 with React 19 and Tailwind CSS v4
- Express.js with TypeScript
- Prisma ORM with PostgreSQL
- Redis for caching
- Google Gemini for AI processing
- shadcn/ui with radix-nova styling
