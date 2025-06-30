
# Cursor AI Coding Instructions
<!-- Converted from VS Code Copilot settings on 2025-06-30 -->

## General Development Practices

### Version Management
- Use the latest version of the libraries.
- Use the latest version of the language.
- Use the latest version of the framework.
- Use the latest version of the operating system, preferring Linux but optimally supporting Windows too.

### Project Context & Code Style
- Detect project context from `package.json`, `requirements.txt`, `go.mod`, `pom.xml`, or `composer.json` to align
  suggestions with existing project patterns and dependencies.
- When contributing to repositories I don't own: Match the existing patterns, coding style, and library choices of the
  project. Don't introduce new dependencies unless explicitly required for the feature or fix.
- For monorepos or multi-service architectures: Consider shared libraries and consistent patterns across services.

### Code Quality & Architecture
- Follow language-specific best practices and design patterns. Write self-documenting code with clear variable names
  and add comments for complex business logic.
- Implement proper separation of concerns, use dependency injection where appropriate, and follow SOLID principles
  for object-oriented code.
- For small projects, scripts, or proof-of-concepts: Use built-in language features and standard library functionality
  unless advanced patterns are specifically needed for the use case.

## Security & Performance

### Security Practices
- Prioritize secure coding practices: validate inputs, sanitize outputs, use parameterized queries, implement proper
  authentication/authorization checks, and avoid hardcoded secrets.
- For enterprise applications: Follow OWASP guidelines and implement security headers, input validation, and proper
  error handling that doesn't expose sensitive information.

### Performance Optimization
- Consider performance implications: use efficient algorithms, avoid unnecessary dependencies, implement proper
  caching strategies, and optimize database queries.
- For resource-constrained environments or serverless functions: Prefer lightweight alternatives and minimize cold
  start times.

## Error Handling & Logging

### General Error Handling
- Add logging (including debug level), and error handling to primary functions. Also create unit tests where
  applicable.
- Implement graceful error handling with user-friendly messages, proper logging for debugging, and fallback
  mechanisms where appropriate.
- For advanced logging and resilience patterns: Only use specialized libraries when the project scope, complexity,
  or production requirements justify it. Consider the project size, ownership context, and whether it's a
  contribution to an existing codebase that doesn't already use these patterns.

### Language-Specific Logging & Resilience

#### TypeScript/JavaScript
- For enterprise or production applications requiring advanced observability and fault tolerance, use Winston for
  logging and Cockatiel for resilience.
- For smaller projects or contributions to existing codebases, use built-in console logging and simple try-catch
  patterns unless the project already employs these libraries.

#### Python
- For enterprise or production applications requiring advanced observability and fault tolerance, use Structlog for
  logging and PyBreaker for resilience.
- For smaller projects or contributions to existing codebases, use the built-in logging module and simple exception
  handling unless the project already employs these libraries.

#### Go
- For enterprise or production applications requiring advanced observability and fault tolerance, use Zap for
  logging and Failsafe-Go for resilience.
- For smaller projects or contributions to existing codebases, use the built-in log package and simple error
  handling unless the project already employs these libraries.

#### Java
- For enterprise or production applications requiring advanced observability and fault tolerance, use Log4j for
  logging and Resilience4j for resilience.
- For smaller projects or contributions to existing codebases, use built-in `java.util.logging` or SLF4J and simple
  exception handling unless the project already employs these libraries.

#### PHP
- For enterprise or production applications requiring advanced observability and fault tolerance, use Monolog for
  logging and PHP-Resilience for resilience.
- For smaller projects or contributions to existing codebases, use built-in `error_log()` and simple exception
  handling unless the project already employs these libraries.

### Resilience Patterns
- Use circuit breaker patterns for external service calls in production applications, but simple retry logic for
  smaller projects.

## Testing & Documentation

### Testing Strategy
- When tests are asked for, generate comprehensive tests: unit tests for business logic, integration tests for
  external dependencies, and end-to-end tests for critical user flows. Include edge cases and error scenarios.
- For test-driven development: Generate failing tests first, then implement code to make them pass.

### Documentation
- Generate appropriate documentation: JSDoc/docstrings for functions, README files for projects, and OpenAPI specs
  for REST APIs.

## API & Frontend Development

### API Design
- Follow RESTful principles for APIs: use appropriate HTTP methods, status codes, and consistent naming
  conventions.

### Frontend Development
- For frontend applications: Include accessibility attributes (ARIA labels, semantic HTML) and consider
  internationalization (i18n) patterns.

## Configuration & Deployment

### Configuration Management
- Use environment variables for configuration, set with a .env file, implement proper configuration validation, and
  provide sensible defaults.
- For containerized applications: Follow 12-factor app principles for configuration and deployment.

### DevOps & Version Control
- Consider .gitignore patterns for generated files and ensure sensitive data exclusion.
- Generate meaningful commit messages following conventional commit format when creating code changes.
- Follow an enterprise GitOps/DevOps methodology for change/PR creation like a senior FAANG developer would.

### Container & Cloud Deployment
- When it is logical to do so, design any multi-tier, hosted, service, or web-based applications and all components
  to run in containers in an OpenShift environment for Production, and Podman for Development, generating Helm
  charts for deployment.

## Formatting & Organization

### Date/Time Formatting
- Unless otherwise indicated, use YYYY-MM-DD format for dates and 24hr time in UX, code comments, documentation,
  and commit messages where appropriate.

### Project Organization
- Put all test scripts, optimization attempts, in-progress alternates, etc. in the `_dev_tests_` subdirectory of the
  project unless they need to be located elsewhere to complete the testing. If this is the case, when complete move
  them to the project `_dev_tests_` directory with a unique filename and comment at the top explaining why/where
  they need to be run.
- Put all agent summaries, reports, and process documentation in the `_dev_docs_` subdirectory of the project.

## Commit Message Guidelines
- Start with a concise one-liner summary, and then use the body to explain the "what" and "why" of the changes, not
  the "how". Assume the reviewer knows the codebase and focus on the intent and impact of the change.
- Use bullet points for lists, and include issue references (e.g., JIRA tickets) if applicable.
- End with a footer for any meta-information like "Reviewed-by" or "Co-authored-by".
