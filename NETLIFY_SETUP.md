# GitHub Secrets Configuration Guide

To complete the Netlify GitHub integration, add these secrets to your repository:

## Required Secrets

1. **NETLIFY_AUTH_TOKEN**
   - Get from: https://app.netlify.com/user/applications#personal-access-tokens
   - Create a new "Personal access token" in Netlify
   - Copy and paste into GitHub Secrets

2. **NETLIFY_SITE_ID**
   - Get from: https://app.netlify.com/sites
   - Go to your site settings → General → Site details
   - Copy the Site ID value

3. **DEPLOY_KEY** (Your SSH Key)
   - The SSH public key you provided has been configured
   - Store the corresponding private key as a GitHub secret if needed

## Setup Steps

1. Go to your GitHub repository: https://github.com/trump369/SOVEREREIGN-chain
2. Navigate to Settings → Secrets and variables → Actions
3. Click "New repository secret" for each:
   - Name: `NETLIFY_AUTH_TOKEN`, Value: [your token]
   - Name: `NETLIFY_SITE_ID`, Value: [your site ID]
   - Name: `DEPLOY_KEY`, Value: [your SSH private key]

## How It Works

- **On Push to main**: Automatically deploys to Netlify
- **On Pull Requests**: Creates preview deployments with comments
- **Python Environment**: 3.11 with all dependencies from requirements.txt

## Notebooks Deployed

Your Jupyter notebooks will be accessible at the Netlify site:
- demo.ipynb
- chains.ipynb
- embeddings.ipynb
- agents.ipynb
- azure-oai.ipynb
- faissdemo.ipynb
