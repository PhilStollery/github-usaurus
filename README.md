# Technical Writer Assessment: Using a docs-as-code approach to submit your writing sample

## Overview

On our project we use a docs-as-code approach to managing our documentation. We use git, Markdown, and Docusaurus to create and maintain our docs. 

This repository is a sample documentation website built using these tools - and you can view the built website here: https://philstollery.github.io/github-usaurus.

Please can you:

1. Clone this repository to your own machine, then push it to your own GitHub account in a private repo.
2. Complete the setup to deploy the website to GitHub Pages.
3. Write a how-to tutorial using our template, that:
    
    - Explains how to deploy a Docusaurus website to GitHub Pages.
    - You can use content from this README.md file as a reference, but please make sure to include step-by-step instructions, screenshots, and any other relevant information to help a non-technical user complete the task.
    - Ensure you follow the structure outlined in our [Tutorial template](https://philstollery.github.io/github-usaurus/docs/templates/template-tutorial).
    - Follow the style outlined in our [Style guide](https://philstollery.github.io/github-usaurus/docs/templates/style-guide).
    - Please don't spend more than 45 minutes on the writing task.
  
4. Publish the changes to your personal repository - and share the link with us to the hosted GitHub pages and your updated repository.
5. Extra credit: Create a pull request back to this repository with your changes for review.

Below are the steps you need to setup the project locally and deploy it to GitHub Pages.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Install node.js (version 14 or higher)
- Install yarn package manager
- Create a free GitHub account if you don't already have one
- Have git configured locally to be able to pull and push to GitHub repositories

## Installation

After you clone this repository locally, navigate to the project directory and run the following command to install the required dependencies:

```bash
yarn
```

## Local development

```bash
yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server. You can use this to preview your changes before building and deploying the site.

## Deployment

You'll need to have created a GitHub personal access token. Follow [this guide](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic) to create one. Grant it `write:packages` and `read:packages` scopes.

1. Set the `NPM_GITHUB_AUTH_TOKEN` environment variable to your GitHub personal access token:

```bash
export NPM_GITHUB_AUTH_TOKEN="YOUR PAT TOKEN"
```

1. Set the `GIT_USER` environment variable to your GitHub username:

```bash
export GIT_USER=<Your GitHub username>
```

1. Create a `gh-pages` branch in your repository if it does not already exist:
  
```bash
git checkout gh-pages
git add .
git commit -m "Initial commit to create a gh-pages branch"
git push -u origin
```

1. Edited the docusaurus.config.ts file to set the correct url and baseUrl for your GitHub pages site. For a repository named `github-usaurus` under the user `philstollery`, the settings would be:

```ts
  // Set the production url of your site here
  url: 'https://philstollery.github.io',
  // Set the /<baseUrl>/ pathname under which your site is served
  // For GitHub pages deployment, it is often '/<projectName>/'
  baseUrl: '/github-usaurus/',

  // GitHub pages deployment config.
  // If you aren't using GitHub pages, you don't need these.
  organizationName: 'philstollery', // Usually your GitHub org/user name.
  projectName: 'github-usaurus', // Usually your repo name.
```

Change the `url`, `baseUrl`, `organizationName`, and `projectName` values to match your GitHub username and repository name respectively.

1. Run the deployment command:

```bash
yarn deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.
