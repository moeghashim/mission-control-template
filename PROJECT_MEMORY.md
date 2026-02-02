# Mission Control — Project Memory

## Purpose
Project-specific memory for Mission Control (Babanuj Ops). Keeps decisions, architecture, and operational notes scoped to this repo.

## Current Stack
- Next.js (App Router)
- Convex (DB + functions)
- Better Auth (email/password) integrated with Convex
- Vercel hosting

## Core UI/Data (Completed)
- Agent cards + nav + KPI snapshot
- Task board w/ full statuses + card details
- Content calendar
- Knowledge base
- Meeting notes hub
- Support queue
- B2B pipeline
- Templates library
- Live feed + approvals queue
- Standups + alerts + audit trail panels
- Admin pages: Add Agent, Create & Assign Task

## Process/Automation (Completed)
- Daily standup generator (summaries + blockers)
- Alerts engine (blocked tasks, pending approvals, support backlog, KPI regression)
- Policy enforcement for approvals
- Audit log automation (rationale/impact/measurement + learning)

## Data Model (Convex)
- agents (name, function, role, operatingStyle, deliverables, status, focus, workload)
- tasks (status, channel, priority, owners, dueDate, brand, KPI, checklist, definition of done, decision log)
- approvals, activities, kpis, supportQueue, b2bPipeline, templates
- contentCalendar, knowledgeBase, meetingNotes
- standups, alerts, policies, auditLogs

## Admin Workflows
- Add Agent page (/agents/new): required fields + markdown import
- Deactivate Agent (captures work summary + learning → audit logs)
- Create & Assign Task (/tasks/assign): creates new task assigned by default

## Deployment Notes
- Convex prod: rosy-snail-488
- When Convex schema changes, deploy to prod to avoid client errors.

## Known Lint Warnings
- useMemo deps warnings (react-hooks/exhaustive-deps) in dashboard and admin form
- Unused eslint-disable directives in Convex generated files

## Latest UX Updates
- Task cards stand out with status color dot + processing gear
- Clickable tasks open a details modal
- Sticky navigation on all pages
- Header buttons for Add Agent / Create Task

## Next
- Optional: Add UI for editing tasks/agents
- Optional: Add filters/search and pagination
