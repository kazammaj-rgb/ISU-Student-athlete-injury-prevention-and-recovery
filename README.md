# Student-Athlete Injury Recovery System

Native PHP and MySQL academic application for protected recovery case documentation and administrative documentation-readiness review. It is not a diagnostic or medical safety tool.

## Requirements
PHP 8.2+, PDO MySQL, MySQL/MariaDB, Apache (XAMPP is suitable). Configure the Apache document root to this repository's `public` directory.

## Local setup
1. Start Apache and MySQL.
2. Import `database/schema.sql` through phpMyAdmin or the MySQL CLI.
3. Copy `config/config.example.php` to `config/config.local.php`; adjust DSN/user/password and replace the sample app key.
4. Browse to the configured Apache URL. Registration creates athlete accounts only.
5. For fictional development/demo records only, run `php database/seeders/demo.php --development-only` from the project root. Demo password is disclosed by the script and must only be used locally; change it before sharing. Do not seed production.

Use `http://localhost/` only when Apache maps the project `public` directory as its web root. Otherwise use the project's configured virtual host. HTTPS is not configured or verified by this repository.

## Implemented
Athlete registration/login with session arithmetic CAPTCHA, password hashing, CSRF validation, role-scoped dashboards and case views, athlete concern submission, clinician review/milestone/follow-up/clearance workflows, explainable documentation readiness evaluations, audit log, admin summary report, help pages, responsive/print CSS, schema, and fictional development seed data.

## Known gaps
User/team/sport administration, pagination/filtering and complete CRUD, notification UI, password reset and login throttling, secure document upload/download, backup and controlled restore, configurable DSS rule management, complete administrative participation approvals, expanded chart/report suite, SSL deployment proof, and complete automated integration tests remain unimplemented. Coach view provides a limited clearance-record indicator and must not be interpreted as an institutional participation approval. Review institutional privacy, consent, retention, and access requirements before real use.

## Documentation
See `docs/PRD.md`, `TRD.md`, `APP_FLOW.md`, `DESIGN_BRIEF.md`, `BACKEND_SCHEMA.md`, `IMPLEMENTATION_PLAN.md`, `USER_MANUAL.md`, and `FEATURE_EVIDENCE.md`. PRD/TRD are also available from the Help menu.

## Verification
Run `php -l public/index.php` and `php -l database/seeders/demo.php`. Import and workflow behavior requires a configured MySQL/MariaDB instance. No test or deployment result should be inferred unless actually run in that environment.
