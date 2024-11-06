# Automated Postman API Testing Workflow

This repository contains an automated GitHub Actions workflow designed to periodically test and submit applications through the Postman API. The setup leverages Postman and Newman to automate API requests, simulating the process of submitting course applications and generating offers at a high frequency. 

## Workflow Overview

The GitHub Actions workflow (`.github/workflows/postman_test.yml`) is scheduled to run every 5 minutes. During each run, it:

1. **Fetches the Latest Postman Collection**: Retrieves the most up-to-date version of the Postman collection via the Postman API to ensure all test cases are current.
2. **Submits Course Applications**: Automates the submission of +20 RMO course applications. Each application simulates a real-life request, creating a dynamic environment for testing application workflows.
3. **Generates Institution Offers**: For each RMO application, it simulates +10 offers from various institutions, providing a comprehensive test of multi-institution application handling.

## How to Check Actions and Results

### Viewing Workflow Runs (Actions)

To monitor the progress and results of the automated tests, follow these steps:

1. Go to the **Actions** tab in your GitHub repository. This tab contains a log of all workflow runs.
2. Select the most recent workflow run to view the details of its execution.
3. You can see if the workflow completed successfully or if there were any errors during execution. The logs will provide detailed information about the workflow steps.

### Locating HTMLEXTRA Test Results

Test results are generated using the **htmlextra** reporter. After each workflow run, you can access the detailed results by:

1. Navigating to the **Actions** tab.
2. Selecting the latest workflow run.
3. Scrolling down to the **Artifacts** section of the workflow run, to find the **Test Results** artifact.
4. Download the `report.html` file to view the detailed test results.

The `report.html` file contains an overview of all the requests made during the workflow execution, including their status, response times, and any failed tests.

### Customizing the Cron Job
The cron job controls how often the workflow runs. By default, the workflow is set to run every 5 minutes using the following cron schedule:

```yaml
cron: '*/5 * * * *'
```

You can customize this schedule by modifying the cron expression. Here are a few examples:

- `cron: '*/10 * * * *'` – This will run the workflow every 10 minutes.
- `cron: '0 * * * *'` – This will run the workflow every hour.
- `cron: '0 0 * * *'` – This will run the workflow once a day at midnight.

For more details on cron expressions, you can refer to the [cron syntax documentation](https://en.wikipedia.org/wiki/Cron#CRON_expression).

## Summary

This automated setup ensures that API tests are continuously validated, providing rapid feedback on the application submission and offer creation endpoints. It supports high-frequency testing, simulating a realistic environment with multiple applications and offers from various institutions.

