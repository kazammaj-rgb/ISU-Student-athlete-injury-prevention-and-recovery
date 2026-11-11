# Academic Feature Evidence Checklist

| Feature | Page | Demonstration | Expected evidence |
|---|---|---|---|
| Authentication | `?page=login` | Wrong password/challenge, then valid demo login | Generic error then role dashboard |
| Dashboard | `?page=dashboard` | Sign in per role | Scoped count and role |
| DSS | `?page=cases` | Clinician records milestone/clearance; admin/clinician evaluates | Stored checks and explanation (show only fictional data) |
| CRUD | `?page=cases` | Athlete submits; clinician adds milestone | Case and milestone records; full CRUD is not yet implemented |
| Print/report | `?page=report` | Admin opens summary and browser print preview | Generated timestamp and aggregate counts |
| Multi-filtering | N/A | Not implemented | Requirement remains unverified |
| SSL | Deployment URL | Inspect certificate in deployed host/browser | Cannot evidence until deployment |
| Password hashing | Registration flow | Inspect source and verify login with sample account | Never publish actual password hashes |
| Activity logs | `?page=logs` | Perform login and case actions | Actor/action/time rows |
| Backup/restore | N/A | Not implemented | Use isolated database only after tools exist; requirement unverified |

Use fictional seed data. Do not claim screenshots or results that were not captured.
