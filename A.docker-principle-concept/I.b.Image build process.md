### 1. How Docker Builds Work (All Builds)
Every instruction (RUN, COPY, etc.) in a Dockerfile creates:

- A temporary container based on the current layer
- Executes the instruction in that container
- Commits the changes as a new layer
- Discards the temporary container


`docker build -t xyz -f Dockerfile.test .`

<img width="300" height="500" alt="deepseek_mermaid_20250813_24b833" src="https://github.com/user-attachments/assets/d13a51fa-ac3c-439b-87ea-bca8361e8783" />

