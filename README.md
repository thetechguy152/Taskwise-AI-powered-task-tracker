# Taskwise: AI-powered task tracker

Taskwise is a full-stack task manager that understands plain English. Type "Send Sam the budget by Friday, it's urgent" and it sets the title, priority and due date for you.

## Features

- **Smart add:** an LLM turns a casual sentence into a structured task.
- **Split into steps:** break any task into 3-6 concrete subtasks with one click.
- **Suggested tasks:** get ideas for what you may be missing, based on your open tasks.
- **Accounts:** register and sign in with email and password. Each user only sees their own tasks.
- **Task basics:** complete, filter, and delete tasks and subtasks, with light and dark modes.

## Tech stack

- **Frontend:** React, Vite
- **Backend:** Node.js, Express
- **Database:** MySQL 8 (users, tasks, subtasks)
- **Auth:** bcrypt password hashing, JWT sessions
- **AI:** Anthropic Claude API, called from the server so the key stays private

## How it works

1. The React app talks to a REST API through a Vite proxy.
2. Express routes check the JWT, then run parameterized MySQL queries scoped to the signed-in user.
3. AI routes send a short prompt to the model, ask for JSON, and return the parsed result to the app.

## Getting started

See [Run it](#run-it) below. You need Node 20.6+, Docker (or any MySQL 8 server), and an Anthropic API key.

## What I learned

- Designing a relational schema with foreign keys and cascading deletes
- Securing an API: password hashing, token auth, per-user data access
- Prompting an LLM for reliable structured output and handling its failures