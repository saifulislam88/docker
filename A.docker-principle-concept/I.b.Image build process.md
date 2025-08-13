### 1. How Docker Builds Work (All Builds)
Every instruction (RUN, COPY, etc.) in a Dockerfile creates:

- A temporary container based on the current layer
- Executes the instruction in that container
- Commits the changes as a new layer
- Discards the temporary container


graph TD
    A[FROM image] --> B[Temp Container 1]
    B --> C[RUN command]
    C --> D[Committed Layer]
    D --> E[Temp Container 2]
    E --> F[COPY files]
    F --> G[Committed Layer]
