# Publish UniHealth HIS online (Render)

This package now includes a Render deployment blueprint and a `/health` endpoint. It is configured to keep its SQLite database on a persistent disk mounted at `/var/data`.

## You must do these steps in your own accounts

1. Extract this ZIP on a computer (or use a GitHub repository). Do not open `index.html` directly. The website and API must run together as a server.
2. Create a private GitHub repository and upload the contents of this folder. Do not upload any existing `.db` file or real patient data.
3. Sign in to Render and choose **New → Blueprint**. Connect the repository and select `render.yaml`.
4. When Render asks for `OWNER_INITIAL_PASSWORD`, enter a new, strong, unique password. Save it securely. Do not reuse your email password.
5. Deploy. Wait until the service is marked **Live**. Render will provide a URL such as `https://unihealth-his.onrender.com`.
6. Open that HTTPS URL on your phone. Sign in using username `odiraedwin220@gmail.com` and the owner password you set in step 4.

## Important

- A Render account and a paid web-service plan with persistent disk are required for this SQLite deployment. Pricing and plan availability can change; check Render's current pricing before creating the service.
- If the database is completely new, the application seeds the Platform Owner account on first startup. If a database already exists, changing `OWNER_INITIAL_PASSWORD` does not reset an existing account's password.
- Keep the GitHub repository private. Never commit `.env`, database files, passwords, API keys, or patient data.
- This is a deployment-ready prototype, not yet approved for real patient records. Before clinical go-live it needs a production database and verified tenant isolation, payment gateway/webhooks, MFA and password reset, backups, monitoring, security testing, and a Kenya health-data/privacy compliance review. Do not enter real patient data until those checks are completed.
