# Technical Requirements Document

## Architecture
Native PHP front controller in `public/index.php`, PDO/MySQL persistence, PHP sessions, server-rendered forms, custom CSS, SQL schema, and documentation under `docs/`. No framework or client-side application code is used.

## PHP and Routes
Routes use the `?page=` query parameter. POST workflows dispatch by a hidden `action` field, verify CSRF tokens, perform prepared SQL operations, write audit events, then redirect. Role checks are server-side.

## HTML/CSS
Semantic HTML forms and tables use responsive CSS Grid/Flexbox and print media rules. There is no JavaScript dependency; users invoke browser print controls.

## Database and Relationships
`database/schema.sql` defines roles, users, sports, teams, athlete profiles, memberships, cases, reviews, milestones, appointments, clearance, participation reviews, DSS rules/evaluations/details, notifications, audit logs, backup records, settings, and document metadata. Foreign keys preserve relationships.

## Authentication and Authorization
Passwords use `password_hash`/`password_verify`, sessions regenerate at login, an arithmetic challenge is stored in session with expiration, and CSRF tokens protect POST. Athlete access is self-scoped; clinician case access includes assigned and unassigned cases; coach access uses roster membership and returns a restricted view. Admin operational pages do not provide clearance editing.

## Privacy and Storage
Configuration must be kept in `config/config.local.php`, outside `public`. `storage/private` and `storage/backups` are outside the document root. Document metadata exists in schema, but upload/download routes are not implemented. Deploy Apache with `public` as document root and HTTPS enabled.

## DSS Rules
The current evaluator checks documented milestone, current clinician clearance, and review status, and persists its explanation and rule reference. Its result is documentation completeness only. Rule editing/version administration UI and explicit expired-clearance outcome differentiation remain future work.

## Reports, Audit, Backup
An admin operational summary and audit table are implemented. Audit captures login/logout and key case actions. SQL export, application ZIP, restore controls, and restoration verification UI are not implemented in this build.

## Deployment, Testing, Maintenance
Import `database/schema.sql`, configure `config/config.local.php`, point Apache to `public`, and enable TLS in the hosting environment. Run `php -l` on PHP files and the supplied test suite. Maintain PHP/MySQL versions and review access, retention, secrets, and backups before real use. No SSL deployment, medical validation, or production security audit is claimed.
