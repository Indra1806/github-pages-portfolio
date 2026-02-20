# Static Website Hosting with GitHub Pages

**Date:** February 21, 2026  
**Topic:** Web Hosting & Static Content Delivery  
**Project:** Syntax Simplified Portfolio Deployment  

## Live Demo
**Access the live website here:** [Live](https://indra1806.github.io/github-pages-portfolio)

## Project Overview
This project demonstrates how to deploy and host a static website utilizing **GitHub Pages**. It showcases a continuous deployment workflow where static assets (HTML/CSS) pushed to a specific repository branch are automatically published to a public URL, completely eliminating the need for traditional server provisioning.

## 1. The 5 W's & How

* **What?** A live, publicly accessible static portfolio webpage hosted natively on GitHub.
* **Why?** To provide a zero-cost, highly reliable hosting solution for static content (like portfolios, documentation, or landing pages) without managing web servers (like Apache or NGINX).
* **How?** By enabling the GitHub Pages feature in the repository settings and targeting the `main` branch. GitHub's internal Actions pipeline automatically builds and serves the content.
* **When?** Used when the application relies entirely on client-side rendering (HTML, CSS, frontend JavaScript) and requires no backend database or server-side execution.
* **Where?** Hosted globally on GitHub's Content Delivery Network (CDN).

## 🛠 Tech Stack
| Component | Technology | Description |
| :--- | :--- | :--- |
| **Markup / Styling** | HTML5 & CSS3 | Application source code |
| **Version Control** | Git | Local source code management |
| **Hosting Platform** | GitHub Pages | Static site hosting service |

## 2. Deployment Architecture

```mermaid
graph LR
    Dev([Developer]) -->|git push| Repo[GitHub Repository: main]
    Repo -->|Triggers| Action[GitHub Pages Build Action]
    Action -->|Deploys to| CDN[GitHub Global CDN]
    CDN -->|Serves| User([End User Browser])
```

## 3. Deployment Steps
**Code Creation:** Authored index.html and style.css in the local workspace.

**Version Control:** Committed the assets and pushed them to the main branch of the remote GitHub repository.

**Pages Configuration:** Navigated to Repository Settings -> Pages.

**Source Selection:** Configured the deployment source to track the main branch at the root / directory.

**Propagation:** Allowed GitHub's automated workflow to build the site and generate the .github.io URL.

## 4. FAQ / Interview Prep
1. What is GitHub Pages? <br>
GitHub Pages is a static site hosting service that takes HTML, CSS, and JavaScript files straight from a repository on GitHub, optionally runs the files through a build process, and publishes a website.

2. Can you host dynamic apps here? <br>
No. GitHub Pages strictly serves static files. It cannot execute server-side languages (like PHP, Python, or Node.js) or connect to backend databases directly. For dynamic apps, you need platforms like Heroku, AWS EC2, or Vercel.

3. What are the limits of GitHub Pages? <br>

    - Repository Size: Maximum of 1 GB. <br>

    - Bandwidth: Hard limit of 100 GB per month. <br>

    - Builds: 10 builds per hour limit. <br>

    - Usage: Intended for personal/open-source projects, not high-traffic commercial businesses.

4. How do you update the website? <br>
The process is continuous. You simply make changes to your local files, commit them, and run git push. GitHub automatically detects the new commit, rebuilds the site, and updates the live URL within a minute or two.
 
5. What happens when you delete the repo? <br>
The website is immediately taken offline, and the URL will return a 404 Not Found error.

6. What is the default file that loads? <br>
When a user visits the root URL, GitHub Pages automatically looks for and serves an index.html file. If index.html is not present, it will fallback to rendering the README.md file as a webpage.

7. Can you use a custom domain? <br>
Yes. You can purchase a domain (e.g., syntaxsimplified.com), navigate to the GitHub Pages settings, enter the custom domain, and then configure your DNS provider (like Route 53 or GoDaddy) with a CNAME or A record pointing to GitHub's IP addresses.
