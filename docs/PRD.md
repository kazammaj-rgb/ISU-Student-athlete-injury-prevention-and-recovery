# Product Requirements Document

## Product Overview
Student-Athlete Injury Recovery System is a native PHP web application for organizing injury concerns, recovery documentation, follow-up records, and return-to-play review support.

## Problem Statement
Paper and disconnected tools make case status, follow-up, and required documentation difficult to coordinate. This application centralizes a limited set of workflows with role-based access.

## Objectives
- Maintain protected athlete profiles and cases.
- Document milestones, appointments, reviews, and clinician-entered clearance.
- Explain administrative documentation checks.
- Present role-scoped case views and printable operational summaries.

## Target Users and Roles
Athletes submit and view their own concerns. Clinicians manage assigned or unassigned cases and record clinical clearance. Coaches see roster-linked case status and a limited clearance indicator. Administrators view operational metrics and logs; they do not receive clinician-only concern notes or clearance editing rights.

## Functional Requirements
Registration is athlete-only; login uses a session arithmetic challenge and password verification. Role-protected pages include dashboard, cases, audit log, reports, PRD/TRD, and user manual. Clinicians can review cases, add milestones, schedule follow-ups, and enter clearance. Admins and clinicians can request a documentation readiness evaluation. Coaches receive participation-facing status only.

## Non-functional Requirements
Native PHP 8.2+, PDO prepared statements, MySQL/MariaDB, password hashing, CSRF checks, output escaping, responsive CSS, accessible labels/focus, and a private configuration file are required. Production deployment requires HTTPS and operational policies for retention and access.

## Scope and Limitations
This is an academic workflow system, not a clinical record system or certified medical product. It does not diagnose, recommend treatment, or assess medical safety. The current implementation provides athlete registration and core case workflows; broad user/team/settings CRUD, password reset, rate limiting, document upload, configurable policies, and complete backup restoration are not implemented.

## Recovery Workflow
Athlete submits a concern; clinician reviews and documents recovery activity; a clinician may record a clearance decision; administrative reviews may evaluate documentation; participation decisions follow institutional policy.

## DSS Process
The DSS checks for a documented milestone, a current clinician clearance record, and a reviewed case. It stores the checks, rule version, evaluator, outcome, and explanation. A documentation result never grants medical clearance or participation approval.

## Acceptance Criteria
A configured installation permits athlete registration/login, role-scoped case access, clinician case actions, audit recording, documentation evaluation, and access to project documentation. Unauthorized route access is rejected. No clinical decision is inferred from a progress percentage or elapsed time.

## Expected Outcomes
Improved organization and explainability for demonstration workflows. No health outcome claims are made.
