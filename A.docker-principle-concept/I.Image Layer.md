## 📦 What Are Docker Image Layers?
Docker images are built using a **layered filesystem**. Each layer represents:

- A set of file changes (added, modified, or deleted files)
- The command that created those changes (`FROM`, `RUN`, `COPY`, etc.)
- A unique cryptographic hash that identifies the layer

### 🔑 Key Characteristics of Layers
- **Immutable** – Once created, layers cannot be changed
- **Cached** – Docker reuses layers when possible to speed up builds
- **Shared** – Multiple images can share the same base layers
- **Read-only** – Running containers add a writable layer on top

## 🧪 Example: Analyzing Image Layers

```dockerfile
FROM alpine:3.14
RUN apk add --no-cache nginx
COPY index.html /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### Layer Breakdown
- **Base Layer**: `alpine:3.14` – Minimal Alpine Linux
- **RUN Layer**: `apk add nginx` – Adds nginx package
- **COPY Layer**: `index.html` – Adds HTML file
- **Metadata Layer**: `EXPOSE`, `CMD` – Configuration only

### 🔍 Viewing Layers in Practice

```bash
docker build -t my-nginx .
docker history my-nginx
```

#### Sample Output:
```text
IMAGE          CREATED         CREATED BY                                      SIZE
a1b2c3d4e5f6   2 mins ago      CMD ["nginx" "-g" "daemon off;"]               0B
f6e5d4c3b2a1   2 mins ago      COPY index.html /usr/share/nginx/html          127B
87654321abcd   2 mins ago      RUN /bin/sh -c apk add --no-cache nginx        5.6MB
...
```

## 🧠 Layer Optimization Tips
- Combine `RUN` commands to reduce layers
- Use `.dockerignore` to avoid unnecessary files
- Use **multi-stage builds**
- Place `COPY` commands last

## 🎯 Why Layers Matter
| Feature          | Benefit                            |
|------------------|-------------------------------------|
| Storage          | Shared layers save disk space       |
| Build Speed      | Layer caching                       |
| Security         | Smaller images = less attack surface|
| Distribution     | Only changed layers are transferred |

---

## 🗃️ Where Docker Stores Image Layers

### 🔎 Default Storage Locations

#### Linux:
```bash
/var/lib/docker/
├── image/        # Image metadata
├── overlay2/     # Default storage driver contents
│   ├── diff/     # Actual layer files
│   ├── layerdb/  # Layer metadata
```

#### macOS/Windows:
- Stored in a hidden VM
- Path inside VM: `/var/lib/docker/`

### 🔍 Check Docker Storage Path
```bash
docker info | grep "Docker Root Dir"
ls -la /var/lib/docker/
```

### Example Directory Structure:
```text
/var/lib/docker/overlay2/
├── abc123.../
│   ├── diff/      # Files
│   ├── lower      # Parent layers
│   └── link       # Short identifier
├── layerdb/
│   ├── sha256/... # Metadata
```

### Important Notes
- ❌ Don't modify these files directly
- ⚠️ Varies with storage drivers: overlay2, aufs, zfs, etc.
- 🧹 Clean up unused layers:
```bash
docker system prune
```


