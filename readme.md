# 🧠 n8n Local Automation Hub

This project sets up a **self-hosted n8n instance** running locally in Docker.  
Use it to build AI agents, connect APIs like OpenAI or Telegram, and automate workflows securely from your own environment.

---

## 🚀 Getting Started

### 1. Clone or Create Project Folder
```bash
mkdir ~/n8n-local
cd ~/n8n-local


=============================================

# 1. Stop the container
docker-compose down

# 2. (Optional) Back up existing data
cp -r ./n8n_data ./n8n_data_backup_$(date +%F)

# 3. Pull the latest image
docker pull n8nio/n8n:latest

# 4. Restart n8n
docker-compose up -d
