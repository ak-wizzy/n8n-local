=================================================================
n8n Docker Deployment
=================================================================

Production-ready Docker deployment for n8n using environment-based configuration.
This repository provides a portable and reproducible setup for running n8n with Docker Compose. It is suitable for home labs, small production environments, and reverse proxy deployments.

The configuration follows a clean infrastructure pattern:
    • Containers are disposable
    • Environment variables define identity
    • Volumes store state
    • Git tracks intent, not runtime data

Overview
This setup supports:
    • Local-only deployments
    • Reverse proxy / domain-based deployments
    • Environment-based configuration
    • Persistent storage using Docker volumes
    • Forward-compatible settings aligned with recent n8n changes

Requirements
    • Docker
    • Docker Compose
    • Optional: Reverse proxy (for domain-based setup)

Setup
    1. Clone the repository.
    2. Create a .env file based on the provided example.
    3. Configure your timezone, authentication credentials, host, webhook URL, and encryption key.
    4. Start the service using Docker Compose.

Important Configuration Notes

Encryption Key
The N8N_ENCRYPTION_KEY must remain consistent across deployments if you intend to migrate or restore backups. Changing this key will make previously saved credentials unreadable.
Host and Webhook URL
N8N_HOST and WEBHOOK_URL must reflect how external services access your instance.
For local development, use localhost.
For production, use your public domain and HTTPS.
Only one host value should be defined per environment.

Security Recommendations
    • Use strong basic authentication credentials
    • Use HTTPS in production
    • Restrict container exposure if using a reverse proxy
    • Keep your encryption key private
