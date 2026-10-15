# Azure Cloud Deployment Using Microsoft Azure App Service

## Project Overview
This project demonstrates deploying and running a Python Flask web application on Microsoft Azure App Service using the Free F1 plan.

## Objectives
- Deploy a Python web application to Azure.
- Configure application dependencies and startup settings.
- Verify application availability using HTTP endpoints.
- Implement health and information endpoints.
- Document deployment evidence for a cloud engineering portfolio.

## Architecture
**User Browser → Azure App Service (F1) → Gunicorn → Flask Application**

## Technologies Used
- Microsoft Azure App Service
- Python 3.12
- Flask
- Gunicorn
- Azure Portal
- GitHub

## Application Endpoints

| Endpoint | Purpose |
|---|---|
| `/` | Displays the application homepage |
| `/health` | Returns application health status |
| `/info` | Returns application and hosting information |

## Deployment Configuration
- **App Service:** `harsh-azure-web-app-2026`
- **Operating environment:** Python 3.12
- **Plan:** Free F1
- **Startup command:** `gunicorn --bind=0.0.0.0:8000 app:app`

## Live Application
https://harsh-azure-web-app-2026.azurewebsites.net/

## Testing and Validation
- Homepage opened successfully.
- `/health` returned a healthy status.
- `/info` returned application information with status `running`.
- Deployment configuration and application files were inspected through Azure tools.

## Screenshots
Project screenshots will be added to the `screenshots/` directory.

## Key Learning Outcomes
- Deploying Python applications to Azure App Service.
- Understanding Flask routes and HTTP endpoints.
- Configuring Gunicorn as a production application server.
- Verifying application health and deployment configuration.
- Documenting cloud deployment work for a technical portfolio.

## Future Improvements
- Automate deployment using GitHub Actions.
- Add structured application logging and monitoring.
- Improve error handling and deployment validation.

## Disclaimer
This project is intended for learning and portfolio development. Resource availability and pricing may change. Verify Azure pricing before changing the hosting plan.
