---
title: "Wisp — Native WhatsApp Desktop Client"
date: "Nov 2026"
tags: ["Go", "SQLite", "Win32", "MCP"]
excerpt: "Lightweight native Windows desktop client for WhatsApp with multiple accounts, local chat history, and a built-in MCP server for AI assistants."
description: "Native Windows WhatsApp client with multi-account support and a built-in MCP server."
category: personal
---

Wisp is a lightweight native Windows desktop client for WhatsApp. It runs multiple accounts side by side, keeps chat history in a local database, and lets AI assistants search chats and send messages through a built-in MCP server.

## What I Did

- Built a native Win32 desktop app that runs multiple WhatsApp accounts side by side
- Stored chat history in a local SQLite database
- Added a built-in Model Context Protocol (MCP) server so AI assistants can search chats and send messages

## Tech Stack

- Go with whatsmeow
- SQLite
- Win32 GUI (lxn/walk) with DirectWrite
- Model Context Protocol (MCP)
