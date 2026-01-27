# Redocly

Redocly is a comprehensive suite of tools designed to enhance API documentation workflows, primarily built around OpenAPI specifications. It originated from tools developed at Rebilly to render OpenAPI definitions into production-ready API reference documentation. Redocly supports the entire API lifecycle, from design and collaboration to governance and developer onboarding, making it particularly valuable for technical writers who manage and create documentation for APIs.

## What is Redocly?

Redocly is recognized as a leading API documentation tool that leverages OpenAPI standards to generate clear, interactive, and user-friendly documentation. It supports all API standards and enables automated pipelines from source control systems like GitHub directly to customer-facing docs. The platform emphasizes docs-as-code workflows, allowing teams to treat documentation as version-controlled code, which promotes agility and collaboration across developers, technical writers, product managers, and other stakeholders.

Redocly's tools help in creating responsive, fast, and SEO-ready documentation while enforcing API governance through rulesets and standards checks. This ensures that API descriptions are consistent, compliant, and easy to maintain.

## Key Components of Redocly

Redocly offers several interconnected products and tools, each addressing different aspects of API documentation and management:

### Redoc

Redoc is an open-source API reference renderer that transforms OpenAPI definitions into interactive, web-ready documentation. It features a modern three-panel layout: navigation on the left, detailed endpoint documentation in the center, and request/response examples on the right. Redoc supports OpenAPI 3.1, 3.0, 2.0, and Swagger formats.

Key features include:

- Auto-generated code samples in multiple languages.

- Support for polymorphism, discriminators, mock servers, and nested schemas with deep links.

- Extensive customization options, such as theme adjustments, hiding sections, or enabling search.

- Integration as a standalone HTML page, React component, or via CLI for building docs.

For example, you can generate documentation using the CLI command: `npx @redocly/cli build-docs openapi.yaml`, which produces a static HTML file. This makes Redoc ideal for embedding API references in websites or portals. See the [Redoc material](/02-api-documentation-tools/Redoc.md) for additional information.

### Redocly CLI

Redocly CLI is an open-source command-line tool for managing OpenAPI descriptions and API lifecycle operations. It runs on Node.js and is essential for tasks like linting, bundling, and enhancing API files.

Main features:

- **Linting and Governance:** Validate APIs against built-in or custom rulesets to enforce standards on every revision.

- **Bundling and Splitting:** Combine multiple OpenAPI files into one or split a large file into logical chunks for better maintainability.

- **Transformation:** Add, remove, or modify content in OpenAPI specs, such as publishing subsets of endpoints or using decorators.

- **Documentation Generation:** Integrate with Redoc to preview and build API docs locally.

This tool is particularly helpful for technical writers as it streamlines the management of complex OpenAPI specs, ensuring they are error-free and optimized for documentation.

### Other Products

- **Reunite:** A collaboration platform for API design, editing, and review, featuring visual side-by-side comparisons, a built-in editor, and single-sourcing for content.

- **Revel (Developer Portal):** A hub for creating personalized developer experiences, including landing pages, guides, integrated search, and analytics to boost API adoption.

- **Reef:** An internal API management platform for discovery, scorecards, and governance to optimize internal API ecosystems.

These components integrate seamlessly, allowing for end-to-end API documentation workflows.

## Getting Started with Redocly

Ensure you have Node.js (v18 or higher) and the latest npm installed. For Docker users, have Docker set up if preferring containerized runs. See the [Docker](/03-developer-ecosystem/docker.md) material for additional information.

### Installation

Install Redocly CLI locally in your project directory for better version control: npm i @redocly/cli@latest. Alternatively, use it at runtime without installation via npx @redocly/cli@latest <command>. Verify the installation by running redocly --version to check the version. For Docker: Pull the image with docker pull redocly/cli and run commands like docker run --rm -v $PWD:/spec redocly/cli lint openapi.yaml.

### Linting an OpenAPI File

Use the lint command to validate your API descriptions and enforce rules: redocly lint openapi.yaml. Customize with options like --format=stylish for readable output or --extends=recommended-strict for stricter rules. Example: redocly lint --config=./redocly.yaml api/*.yaml to lint multiple files using a custom config. Generate an ignore file with --generate-ignore-file to suppress specific issues.

### Building Documentation

Generate a standalone HTML file with redocly build-docs openapi.yaml, outputting to redoc-static.html by default. Customize output: redocly build-docs openapi.yaml -o custom-docs.html --title="My API Docs" --theme.openapi.disableSearch to set a title and hide the search box. Use a custom template with -t custom.hbs for advanced styling.

### Next Steps

Create a simple openapi.yaml file (e.g., with basic info and paths) to test. Explore advanced features by signing up for a Redocly account to access hosted tools like the Developer Portal. Integrate into CI/CD pipelines for automated linting and builds. For full guides, refer to the official documentation or GitHub repositories.

## Benefits for Technical Writers

For technical writers focused on API documentation, Redocly offers several advantages:

- **Efficiency:** Automate updates to API references with minimal manual effort, using docs-as-code to keep documentation in sync with code changes.

- **Quality Assurance:** Built-in linting and governance ensure consistent, high-quality docs that adhere to standards.

- **Collaboration:** Tools like Reunite facilitate team reviews and single-sourcing in Markdown, reducing silos between writers and developers.

- **User Experience:** Generate interactive, searchable docs that improve developer onboarding and API adoption.

- **Flexibility:** Support for local previews, static builds, and integration with CI/CD pipelines aligns with modern tech stacks like Docker and Kubernetes.

## Conclusion

This overview provides a foundational understanding of Redocly, equipping technical writers with the knowledge to incorporate it into their documentation practices.

**Futher Resources**

- Official Website: [Redocly](https://redocly.com/)

- Redoc GitHub: github.com/Redocly/redoc

- Redocly CLI GitHub: github.com/Redocly/redocly-cli

- OpenAPI Initiative: openapi.org