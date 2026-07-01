# Architectural Quality & Implementation Standards

When generating system modifications or processing updates under this skill, enforce these exact development rules:

### 1. Clean Architectural Boundaries
- Keep business domain logic completely isolated from transport wrappers, routing frameworks, or database infrastructure layers.
- Write modular, highly cohesive, single-responsibility files that support automated isolation testing.

### 2. Asynchronous Controls
- Enforce strict `async/await` handling across all filesystem, database, IO operations, and script invocations.
- Never write code that blocks the main thread or causes background stall states during long-running background tasks.

### 3. Error Safeguards
- Prevent silent error catching. Wrap operations in try/catch boundaries that log clear contextual failure state data without dropping execution threads.
