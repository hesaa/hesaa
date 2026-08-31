---
title: "TST — Project Management System"
date: "Feb 2026"
tags: ["TypeScript", "Next.js", "Prisma", "MySQL", " shadcn/ui"]
excerpt: "Full-stack project management platform for tracking customers, agreements, purchase orders, work orders, and invoicing with role-based access control."
description: "Full-stack project management platform for enterprise operations."
category: personal
---

TST is a full-stack project management system built to manage the entire lifecycle of enterprise projects — from customer agreements and purchase orders to work execution, document tracking, and invoicing.

## What I Did

- Designed and implemented a comprehensive data model with 20+ entities covering customers, agreements, projects, purchase orders, work orders, SPK, collections, and invoices
- Built role-based access control with NextAuth and custom permission system
- Created dynamic dashboards with Chart.js and Recharts for project progress and financial tracking
- Implemented document progress tracking with milestone-based workflow and audit history
- Developed SPK (work order) management with disbursement tracking and approval flows
- Built invoice generation with PDF export using jsPDF and Excel export with ExcelJS
- Designed responsive UI with shadcn/ui components and Tailwind CSS

## Tech Stack

- Next.js 15 with React 19 and Tailwind CSS v4
- Prisma ORM with MySQL
- NextAuth with custom RBAC
- shadcn/ui with Radix primitives
- Chart.js and Recharts for data visualization
- ExcelJS and jsPDF for report generation
- Zod for validation
