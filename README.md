# GitHub Actions Workflow for HTML Validation and Deployment

This GitHub Actions workflow automates the process of validating and deploying an HTML file. It consists of two primary jobs: validate and deploy. This workflow triggers every time changes are pushed to the main branch.

## Jobs

### 1. Validate Job
The validate job ensures that the HTML file meets certain criteria before deployment. It runs on an ubuntu-latest environment and performs the following checks:

- HTML file existence: The workflow checks if the index.html file exists in the repository. If not, it exits with an error.
- Form validation: The presence of a <form> element with the id="contact-form" is verified. If the form is missing, the workflow fails.
- Name field validation: The existence of an input field with id="name" is checked. If the field is absent, the workflow exits with an error.
- Once these validations pass, a message is displayed confirming the successful validation, and a simulated optimization step creates an optimized version of the index.html file (named optimized_index.html).

### 2. Deploy Job
After successful validation, the deploy job is triggered to deploy the content to GitHub Pages. It runs only if the validate job succeeds. The deployment steps include:

- Checking out the repository code.
- Using the peaceiris/actions-gh-pages action to deploy the HTML files to GitHub Pages, where the optimized HTML file will be published.

## Usage
This workflow automates HTML validation and deployment, making it easier to ensure quality and consistency before publishing updates to your website. Simply push changes to the main branch, and the workflow will handle the validation and deployment process.


## Why the Last Commit Failed?
The most recent commit triggered an error during the validate job because the index.html file did not meet the required validation criteria.
As a result, the workflow exited with an error, and the changes were not deployed to GitHub Pages. You can resolve these issues by ensuring that the required HTML elements are present in the file before pushing again.
