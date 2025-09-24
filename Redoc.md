# Redoc

Redoc is a free, open-source tool for generating beautiful, interactive, and human-readable API documentation from an OpenAPI specification. Its primary goal is to make API documentation easy to read and navigate for end-users (developers).

It takes an OpenAPI definition file (in YAML or JSON format) and transforms it into a clean, three-panel static HTML page that includes a navigation menu, endpoint descriptions, and code examples.

- **Official GitHub Repository:** [Redoc on GitHub](https://github.com/Redocly/redoc)
- **Documentation:** [Redoc: Open source API documentation tool](https://redocly.com/docs/redoc)

## Key Concepts (Q&A Format)

This section covers common questions about Redoc that are useful for understanding its role and application in technical writing and documentation development.

### 1. What is Redoc and what problem does it solve?

**Answer:** Redoc is an open-source tool that visualizes OpenAPI specifications. It solves the problem of presenting complex API information in a structured and easily digestible format. It automatically generates a static HTML documentation website from a single `openapi.yaml` or `openapi.json` file, ensuring that the documentation is always in sync with the API's source of truth.

### 2. How does Redoc differ from Swagger UI?

**Answer:** Both Redoc and Swagger UI generate documentation from an OpenAPI specification, but they have different philosophies:

- **Swagger UI:** Focuses on interactivity. Its most prominent feature is the built-in "Try it out" console, which allows users to make live API calls directly from the documentation. Its design is more functional.
- **Redoc:** Prioritizes **readability and presentation**. It features a three-panel layout (navigation, content, code samples) that many find cleaner and more user-friendly for learning and exploring an API. The open-source version of Redoc does not have a built-in "Try it out" console.

### 3. What input file does Redoc require?

**Answer:** Redoc requires a single OpenAPI specification file. This file serves as the single source of truth and is typically named `openapi.yaml` (for YAML format) or `openapi.json` (for JSON format).

### 4. How can you customize Redoc?

**Answer:** Redoc offers various customization options that can be configured in the main HTML file. This demonstrates practical experience with the tool. Common customizations include:

- Changing the theme colors.
- Adding a custom logo.
- Adjusting scroll behavior.
- Configuring the order of tags and operations.
- Hiding specific sections of the documentation.

### 5. How does Redoc fit into a "Docs-as-Code" workflow?

**Answer:** Redoc is an excellent tool for a Docs-as-Code approach because:

- The OpenAPI specification file can be stored and versioned in a Git repository alongside the application code.
- Any changes to the API (e.g., a new endpoint) are first updated in the specification file.
- The documentation website can be automatically rebuilt and deployed through a CI/CD pipeline whenever the specification file is updated. This ensures the documentation remains accurate and consistent with the actual API.

---

## Getting Started Use Case: Documenting a New API

Let's walk through a typical workflow for a developer or technical writer using Redoc to document a new feature.

**Scenario:** A development team has just added a new set of endpoints (e.g., `/users/{id}`) to their project. The goal is to update the public-facing API documentation.

1.  **Update the OpenAPI Specification:** The first step is to describe the new endpoints in the `openapi.yaml` file. This includes:
    - Adding the path (e.g., `/users/{id}`).
    - Defining the HTTP method (`GET`).
    - Specifying parameters (like the `id` path parameter).
    - Describing possible responses (e.g., `200 OK`, `404 Not Found`).
    - Providing schemas for the request and response bodies.
    - Writing clear `summary` and `description` texts for human understanding.

2.  **Commit to Version Control:** The updated `openapi.yaml` file is committed to the project's Git repository. This is a key step in the "Docs-as-Code" methodology.

3.  **Local Preview (Optional but Recommended):** The author runs Redoc locally to preview the changes. They can check for typos, rendering issues, and ensure the new documentation looks correct before publishing. This is often done using a local web server.

4.  **Generate the HTML File:** A command is run to bundle the `openapi.yaml` file with Redoc into a single, zero-dependency HTML file. The command often looks like this:
    ```bash
    npx redoc-cli build openapi.yaml -o index.html
    ```

5.  **Deploy the Documentation:** The generated `index.html` file is deployed. This step is usually automated with a CI/CD pipeline (like GitHub Actions), which triggers on every commit to the main branch. The pipeline builds the file and pushes it to the hosting server.

**Result:** The live API documentation portal is now updated with the new `/users/{id}` endpoint, and the documentation is perfectly in sync with the API's definition.

---

## How to Deploy Redoc Documentation

Once you have your `openapi.yaml` file, you need to publish the generated documentation. Here are three common methods.

### Method 1: Standalone HTML File (The Simplest Way)

This method bundles Redoc and your OpenAPI spec into a single HTML file that you can send to anyone or host anywhere.

1.  **Install `redoc-cli`:**
    ```bash
    npm install -g redoc-cli
    ```

2.  **Run the build command:**
    ```bash
    redoc-cli build path/to/your/openapi.yaml --output redoc.html
    ```

3.  **Deploy:** You now have a `redoc.html` file. You can upload this file to any static web hosting service, like Netlify, Vercel, or even an AWS S3 bucket.

### Method 2: Add to an Existing Website (Using a CDN)

If you already have a documentation portal or website, you can easily embed Redoc in one of its pages.

1.  **Create an HTML page** (e.g., `api-docs.html`).
2.  **Add the following HTML snippet.** This code creates a `div` for Redoc to render in and points to your OpenAPI file URL. The Redoc JavaScript library is loaded from a CDN.

    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <title>API Documentation</title>
        <meta charset="utf-8"/>
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <style>
          body { margin: 0; padding: 0; }
        </style>
      </head>
      <body>
        <div id="redoc-container"></div>
        
        <script src="[https://cdn.redoc.ly/redoc/latest/bundles/redoc.standalone.js](https://cdn.redoc.ly/redoc/latest/bundles/redoc.standalone.js)"> </script>
        
        <script>
          Redoc.init('URL_TO_YOUR_OPENAPI.yaml', {
            // optional options object
            scrollYOffset: 50
          }, document.getElementById('redoc-container'))
        </script>
      </body>
    </html>
    ```
3.  **Important:** Replace `URL_TO_YOUR_OPENAPI.yaml` with the public URL where your specification file is hosted (e.g., on GitHub, S3, etc.).

### Method 3: Automate with GitHub Pages

This is a very popular "Docs-as-Code" method. You can set up a GitHub Action to automatically build and deploy your documentation every time you update your OpenAPI file.

1.  **Place your `openapi.yaml`** file in your GitHub repository.

2.  **Create a GitHub Actions workflow file** at `.github/workflows/deploy-redoc.yml`:

    ```yaml
    name: Deploy Redoc to GitHub Pages

    on:
      push:
        branches:
          - main # Trigger the action on push to the main branch

    jobs:
      deploy:
        runs-on: ubuntu-latest
        permissions:
          contents: write # Needed to deploy to gh-pages
        steps:
          - name: Checkout code
            uses: actions/checkout@v3

          - name: Build Redoc documentation
            uses: redocly/cli/actions/build-docs@v1
            with:
              entrypoint: path/to/your/openapi.yaml # Path to your spec file
              output: docs/index.html

          - name: Deploy to GitHub Pages
            uses: peaceiris/actions-gh-pages@v3
            with:
              github_token: ${{ secrets.GITHUB_TOKEN }}
              publish_dir: ./docs
    ```

3.  **Configure GitHub Pages:** In your repository settings under "Pages", set the source to deploy from the `gh-pages` branch (which the action will create and manage for you).

Now, every time you push a change to your `openapi.yaml` file on the `main` branch, the documentation website will automatically update.

---

## Limitations & When to Consider Alternatives

While Redoc is an excellent tool, it's important to understand its limitations to choose the right tool for the job.

### Key Limitations of Open-Source Redoc:

1.  **No "Try It Out" Console:** The most significant difference compared to Swagger UI. If you need users to test API endpoints interactively directly from the documentation, you would need to add a custom solution or use a different tool. (Note: Redocly's paid version includes this feature).
2.  **Single Page Only:** Redoc generates a single, self-contained HTML page. This is great for simplicity but can be limiting if you need a full documentation portal with multiple pages, articles, guides, and tutorials alongside the API reference.
3.  **Limited Search:** The default search (Ctrl+F) works, but it's not as powerful as dedicated search solutions like Algolia that you might find in larger documentation portals.

### When to Look for Alternatives (like Docusaurus, MkDocs, or Redocly's Portal):

- **You need more than just an API reference:** If your documentation requires extensive tutorials, "Getting Started" guides, conceptual articles, or a blog, a static site generator (SSG) is a better choice. You can often integrate Redoc *into* a site built with an SSG, but the SSG manages the overall structure.
- **You manage multiple APIs:** For a complex developer portal that needs to present documentation for many different APIs, a more robust solution like Redocly's paid platform might be necessary to manage them efficiently.
- **Interactive tutorials are a must:** If hands-on, interactive API calls are a core part of your user onboarding, Swagger UI or a platform with an integrated API console might serve you better out-of-the-box.

**Conclusion:** Redoc is the perfect choice for generating a clean, professional, and easy-to-read API reference. For building comprehensive developer portals, it's best used as one component within a larger documentation ecosystem.
