# ProChangeLog App

ProChangeLog is a project changelog and context platform designed to make project history easier to record, understand, and retrieve.

The frontend provides the user interface for managing tenants, clients, projects, user profiles, and project changelogs. It communicates with the backend through defined API contracts.

## Objectives

* Provide a clear and consistent interface for ProChangeLog's business capabilities.
* Support public and private project experiences where applicable.
* Keep presentation responsibilities separate from business rules and backend implementation.
* Allow the interface to evolve without unnecessarily coupling features together.
* Establish a maintainable foundation for future project documentation and context capabilities.

## Technology Stack

* **React** — UI development
* **TypeScript** — static typing
* **Vite** — development server and build tooling
* **React Router** — client-side routing
* **Tailwind CSS** — utility-based styling
* **Custom CSS** — application-specific styling and customization
* **HTTP API** — communication with the backend

The application uses React directly without Next.js. Routing, styling, and other frontend capabilities are introduced through their respective packages rather than through a mandatory full-stack framework.

## Business Capabilities

The frontend supports the following capabilities as they are implemented:

* **Tenant Management** — tenant-related information, invitations, and membership workflows.
* **Client Management** — client records within a tenant.
* **IAM** — account-related and authentication experiences exposed by the backend.
* **User Management** — registration and user profile management.
* **Project Management** — project information, membership, and visibility.
* **Changelog Management** — recording and viewing changes associated with projects.

The frontend represents these capabilities. Business ownership, validation, and authoritative rules remain on the backend.

## Architecture Principles

### Separation of Responsibilities

UI components, navigation, API communication, and presentation-specific behavior should have clear responsibilities.

Components should not independently reproduce business rules that belong to the backend.

### Business-Aligned Structure

Organize frontend features around their actual responsibilities and identities. Avoid grouping unrelated functionality into generic components merely because they share a technical implementation.

### Explicit Dependencies

Features should communicate through defined interfaces and contracts. Avoid unnecessary dependencies between unrelated features.

### Meaningful Naming

Names should communicate the component's actual purpose. Avoid vague names such as `CommonHelper`, `DataProcessor`, or `BaseManager` when a precise name can express the responsibility.

### Maintainable Styling

Use Tailwind CSS where it improves development efficiency and custom CSS where application-specific behavior or styling requires it.

Avoid introducing a UI framework that unnecessarily restricts customization.

## Development Setup

### Requirements

* Node.js compatible with the project dependencies
* npm
* Access to the ProChangeLog backend

### Installation

Clone the frontend repository and install its dependencies:

```bash
git clone <frontend-repository-url>
cd <frontend-project-directory>
npm install
```

Create the required environment configuration using the project's environment template. Configure the backend API base URL according to the application's environment configuration.

For example, if the project defines `VITE_API_BASE_URL`:

```dotenv
VITE_API_BASE_URL=http://localhost:8000
```

Use the actual environment variable expected by the implementation.

### Run the Development Server

```bash
npm run dev
```

### Build for Production

```bash
npm run build
```

### Run Tests

```bash
npm test
```

The test command depends on the test runner configured in the repository.

## Configuration and Security

* Keep environment-specific configuration outside committed secrets.
* Do not place private API keys, signing secrets, or backend credentials in frontend environment variables.
* Treat browser-side validation as a usability feature, not a replacement for backend validation.
* Handle authentication state and failed API requests consistently.
* Respect backend authorization and visibility rules.

Variables exposed through Vite's `VITE_` prefix are included in client-side code and must not contain secrets.

## Development Guidelines

* Follow the established project structure and naming conventions.
* Reuse existing components when their responsibilities and semantics match.
* Avoid unnecessary abstraction and duplicated business logic.
* Keep API contracts explicit.
* Test meaningful user workflows and important UI behavior.
* Do not introduce additional architectural layers without a clear reason.

## Future Direction

Potential extensions include:

* Richer public project changelog pages.
* Project context and overview pages.
* Links to external project resources and documentation.
* Additional project discovery and collaboration capabilities.
* Integrations with development tools.

These extensions should not unnecessarily expand the initial MVP scope.

## Related Documentation

Refer to the project's documentation for finalized API contracts, architecture decisions, capability definitions, and development conventions.
