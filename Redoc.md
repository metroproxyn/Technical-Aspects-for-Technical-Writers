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