# UniHealth HIS — Operational application

This package is a runnable full-stack application, not the earlier localStorage-only prototype.

## Stack
- Node.js + Express
- SQLite with server-side data storage
- JWT authentication
- bcrypt password hashing
- Helmet security headers
- Role-based access control
- Institution/tenant ownership on records
- Audit logging

## Main workflows
- Student reception uses Student ID.
- Staff patients use Staff ID.
- Reception records insurance/medical-cover status.
- Received patients enter the clinician/nurse queue.
- Clinical users create consultations.
- Prescriptions can only use medicines with current stock; stock is deducted transactionally.
- Institution Admin registers staff and assigns Staff IDs.
- Institution subscription and first-payment activation gate access.
- Platform Owner can create/activate institutions and inspect audit records.

## Platform Owner
Owner email/username: `odiraedwin220@gmail.com`
Initial password: `OwnerChangeMe!2026`

The owner can approve/suspend institutions and create institution records from Owner Control. Change the initial owner password before deployment. For production, replace this seed with a proper account setup and password reset/MFA flow.

## Demo login
Institution Admin: `admin` / `Admin123!`
Clinical Officer: `clinician` / `Clinician123!`
Receptionist: `reception` / `Reception123!`

Change all demo credentials before any real deployment.

## Run locally
1. Install Node.js 18+.
2. Open this folder in a terminal.
3. Run `npm install`.
4. Run `npm start`.
5. Open `http://localhost:3000`.

## Production work still required before handling real patient data
- PostgreSQL or managed database for production scale.
- Strong secret management and rotation.
- HTTPS/TLS and production reverse proxy.
- MFA and password-reset flows.
- Payment provider integration and verified webhooks, with settlement to the platform owner's merchant/bank account.
- Email/SMS notifications as required.
- Cloud backups and disaster recovery.
- Stronger server-side tenant isolation, ideally database Row Level Security.
- Detailed clinical modules, laboratory, billing, reporting, document uploads and prescription/dispensing workflows as required by the institution.
- Security testing, penetration testing, monitoring and privacy/data-protection compliance review before go-live.

Never store bank login credentials in this application. A payment gateway/merchant account should handle collection and settlement.
