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

1. Azure App Service Overview

<img width="1917" height="927" alt="app overview" src="https://github.com/user-attachments/assets/9274a13d-23d5-42e2-9d47-50805afe63e4" />

2. Deployed Application Homepage

<img width="1917" height="1018" alt="live application hoempage" src="https://github.com/user-attachments/assets/9bede776-223b-4583-b84c-ad6ae9ca1603" />

3. Application Health Check
   <img width="1917" height="1007" alt="health-endpoints" src="https://github.com/user-attachments/assets/67aeb862-032b-4cf9-94f4-ab5c35110a4d" />


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


---

## Project : Azure CI/CD with GitHub Actions

### Objective
Automate the deployment of a Python Flask web application to Azure App Service using GitHub Actions and secure OpenID Connect (OIDC) authentication.

### Architecture

Developer → GitHub Repository → GitHub Actions Workflow → Azure Login (OIDC) → Azure App Service → Live Flask Application

### Technologies Used
- Microsoft Azure App Service (F1 Free Plan)
- GitHub Actions
- GitHub
- Python 3.12
- Flask
- Azure CLI
- Microsoft Entra ID
- OpenID Connect (OIDC)

### Implementation
1. Used the existing Flask application and Azure App Service.
2. Created a GitHub Actions workflow at `.github/workflows/azure-deploy.yml`.
3. Configured workflow triggers for pushes to the `main` branch and manual execution.
4. Configured OIDC authentication between GitHub Actions and Microsoft Entra ID.
5. Assigned the `Website Contributor` role at the App Service scope.
6. Installed Python dependencies and packaged `app.py` and `requirements.txt`.
7. Deployed the package to Azure App Service using Azure CLI.
8. Verified the deployment through the live application endpoints.

### Security
- Used OIDC federation instead of a stored Azure client secret or publish profile.
- Configured a federated credential for the repository's `main` branch.
- Restricted the deployment identity's role assignment to the target App Service.

### Verification Results
- GitHub Actions workflow: Successful
- Azure authentication: Successful
- Azure App Service deployment: Successful
- `/health` endpoint: Returns healthy JSON
- `/info` endpoint: Returns application and platform information

### Skills Demonstrated
- CI/CD pipeline configuration
- GitHub Actions automation
- Azure App Service deployment
- Microsoft Entra ID application and service principal configuration
- OIDC workload identity federation
- Azure role-based access control (RBAC)
- Python application packaging and deployment
- Post-deployment verification

### Outcome
Implemented and verified an automated deployment pipeline that publishes a Flask application to Azure App Service when changes are pushed to the `main` branch, with a manual deployment option.

