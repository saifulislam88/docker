## 🐳 Docker RUN vs CMD vs ENTRYPOINT

### 1️⃣ RUN
**Purpose:** Executes commands at image build time to install software, set up environment, or prepare the image.

- Creates a new image layer each time it’s used.
- Runs once during `docker build`, not when the container starts.

**Example (Shell Form)**
```dockerfile
RUN apt-get update && apt-get install -y python3
```

**Example (Exec Form)**
```dockerfile
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "vim"]
```

✅ **Benefits**
- Used for image preparation.
- Keeps final image ready for execution.

⚠ **Problems**
- Each RUN creates a layer → can increase image size if not optimized.

---

### 2️⃣ CMD
**Purpose:** Provides default command/arguments for the container when it starts.

- Only one CMD is effective — last one in Dockerfile overwrites earlier ones.
- Overridden easily by arguments in `docker run`.

**Example (Only CMD)**
```dockerfile
FROM alpine
CMD ["echo", "Hello World"]
```
```bash
docker run myimg              # Hello World
docker run myimg echo Goodbye # Goodbye
```

**Example (With ENTRYPOINT)**
```dockerfile
FROM python:3.8-slim
ENTRYPOINT ["python"]
CMD ["app.py"]
```
```bash
docker run myimg         # python app.py
docker run myimg test.py # python test.py
```

✅ **Benefits**
- Flexible, easy to override.
- Good for dev/testing containers.

⚠ **Problems**
- In prod, accidental overrides may break startup.

---

### 3️⃣ ENTRYPOINT
**Purpose:** Defines the main executable for the container — always runs unless overridden with `--entrypoint`.

- Arguments passed via `docker run` are appended to ENTRYPOINT.
- Often combined with CMD for default args.

**Example (Only ENTRYPOINT)**
```dockerfile
FROM alpine
ENTRYPOINT ["echo", "Hello"]
```
```bash
docker run myimg       # Hello
docker run myimg World # Hello World
```

**Example (Recommended: ENTRYPOINT + CMD)**
```dockerfile
FROM alpine
ENTRYPOINT ["echo"]
CMD ["Hello World"]
```
```bash
docker run myimg              # Hello World
docker run myimg "Bye World"  # Bye World
```

✅ **Benefits**
- Enforces correct startup command in prod.
- Prevents accidental overrides of the main process.

⚠ **Problems**
- Less flexible for debugging; must override with `--entrypoint` if needed.

---

## 4️⃣ Shell Form vs Exec Form
- **Shell Form** (`CMD command param`) → runs in `/bin/sh -c` (Linux) or `cmd /S /C` (Windows).
- **Exec Form** (`CMD ["command", "param"]`) → runs directly, better for signal handling (important in prod).

**Best Practice** → Use exec form for ENTRYPOINT and CMD in production.

---

## 5️⃣ Which to Use in Production?
- **Use ENTRYPOINT** for the main executable → ensures container runs the intended app every time.
- **Use CMD** for default arguments → lets you change behavior without rebuilding the image.

**Pattern:**
```dockerfile
ENTRYPOINT ["python", "/app.py"]
CMD ["--port", "8080"]
```
