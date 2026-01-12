# Onboarding: Local Secret Management for .NET Solutions

This guide assumes that you have the prerequisite software, have cloned the repository, and are viewing the .NET solution within Visual Studio. This document ensures that each developer has the required local configuration values without storing any sensitive information in source control.

## Step 1 – Identify Application Projects

1. In the Solution Explorer, identify the **application** projects (those that produce an executable):  
   - Examples: Web API, Blazor app, console app.  
   - Class libraries do **not** define their own secrets; they use configuration from the app that references them.
2. For each application project, open the `.csproj` file and confirm it contains a `<UserSecretsId>...</UserSecretsId>` element.  
   - Do **not** change these IDs; they are shared across the team.

## Step 2 – Create Local User Secrets Files

You should repeat step 2 for each application project within the .NET solution.

1. ==Right‑click the application project in Solution Explorer.==  
2. Choose **Manage User Secrets**.  
   - Visual Studio will create (or open) a `secrets.json` file associated with that project’s `UserSecretsId`.  
   - This file is stored outside the repo, under your user profile, so it will not be committed.

> Tip: If you are not using Visual Studio, you can run `dotnet user-secrets init` and `dotnet user-secrets set` from the project directory to achieve the same result.

## Step 3 – Populate Required Secrets

1. Refer to the project’s configuration documentation (for example, `docs/configuration.md` or an example secrets file) to see which keys are required.  
2. Copy the keys into your `secrets.json` file and fill in your local values, following the documented structure.

Example structure:

```json
{
  "ConnectionStrings": {
    "Default": "Server=...;Database=...;User Id=...;Password=..."
  },
  "Auth": {
    "ClientId": "your-local-client-id",
    "ClientSecret": "your-local-client-secret"
  }
}
```

3. Save the `secrets.json` file. Your values remain local and private to your machine.


## Quick Checklist for New Developers

- [ ] Repo cloned and solution opens in Visual Studio. 
- [ ] Application projects identified (Web API, Blazor, console, etc.).
- [ ] `UserSecretsId` confirmed in each application `.csproj` without modification.
- [ ] `secrets.json` created for each app via **Manage User Secrets**.
- [ ] Required keys added to `secrets.json` using documented structure.
- [ ] Application runs locally in Development without missing-secret errors.  
- [ ] No real secrets added to any tracked configuration files.
