# Langfuse integration

## Official Langfuse agent skill

The official Langfuse skill from [langfuse/skills](https://github.com/langfuse/skills) is installed in `.agents/skills/langfuse/`.

The skill includes:
- `SKILL.md`: entry point and workflow guidance.
- `references/instrumentation.md`: guidance for tracing an existing application.
- Additional references for evaluations, prompt management, user feedback, CI/CD, and Langfuse CLI use.

## Application tracing status

This repository currently contains no application source code or dependency manifest. Therefore, no SDK/framework integration has been added yet. The next step is to add or point to the actual application code, identify the existing model/framework integration, and instrument its request path with Langfuse rather than introducing a separate demo app.

## Credentials

Do not commit API secrets. Configure `LANGFUSE_PUBLIC_KEY`, `LANGFUSE_SECRET_KEY`, and the appropriate `LANGFUSE_BASE_URL` (or supported host variable) in the application's local environment or secret manager. Do not expose the secret key to browser/client code.

## Verification requirements

After tracing is added to the application:
1. Run a representative request end-to-end.
2. Confirm the trace arrives in the correct Langfuse project.
3. Check descriptive trace names, nested spans/generations, model and token usage where available, meaningful inputs/outputs, and sensitive-data redaction.
4. Inspect the resulting trace against the current [Langfuse observability best practices](https://langfuse.com/docs/observability/best-practices).
