# Test Repository for Auto-Shutdown Scripts

This repository is designed to test and demonstrate automation scripts for managing environment shutdown exclusions. It provides a structured way to request that certain environments not be automatically shut down during specified time periods.

## Purpose

The primary purpose of this repository is to:

- Test automatic processing of environment shutdown exclusion requests
- Demonstrate GitHub workflow automation for processing structured issue forms
- Handle requests to keep environments running outside of normal operating hours

## How It Works

### Requesting an Environment Shutdown Exclusion

To request that an environment not be automatically shut down:

1. Create a new issue using the "🌍 Skip auto shutdown" template
2. Fill in the required information:
   - Change or Jira reference
   - Justification for the exclusion
   - Business area (CFT or Cross-Cutting)
   - Team/Application name
   - Environment(s) to exclude from shutdown
   - Start date (format: DD-MM-YYYY)
   - End date (format: DD-MM-YYYY)
   - Whether the exclusion is needed past 11pm

### Available Environments

The following environments can be selected for shutdown exclusion:

- Sandbox
- AAT / Staging
- Preview / Dev
- Test / Perftest
- Demo
- ITHC
- PTL

### Automated Processing

When an issue is created or updated, a GitHub workflow automatically:

1. Extracts form data from the issue
2. Updates a GitHub Project board with the request information
3. Modifies the issue title to include key information for easy reference
4. Processes cancellation requests if a 'cancel' label is added

## Technical Implementation

The repository contains:

- Issue templates: Located in `.github/ISSUE_TEMPLATE/` defining the form structure
- Workflow files: Located in `.github/workflows/` containing the automation logic
- Example implementation: `example.yml` demonstrates the automation process

## Notes

- If you need environments for weekends, include Friday in your start date
- The default exclusion keeps environments running until 11pm; specify if you need longer
- Requests can be cancelled by adding the 'cancel' label to the issue