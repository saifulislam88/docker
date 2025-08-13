### Multiple CMD
- **Allowed?** ✅ Yes, but **only the last CMD** in the Dockerfile is used.
- All earlier CMD instructions are ignored because CMD is stored as image metadata and gets overwritten.

**Example:**
```dockerfile
FROM alpine
CMD ["echo", "Hello"]
CMD ["echo", "Goodbye"]
```
Running:
```bash
docker run myimg
```
Output:
```
Goodbye
```

### Multiple ENTRYPOINT
- **Allowed?** ✅ Yes, but **only the last ENTRYPOINT** takes effect.
- Earlier ENTRYPOINT instructions are ignored for the same reason as CMD.

**Example:**
```dockerfile
FROM alpine
ENTRYPOINT ["echo", "Hello"]
ENTRYPOINT ["echo", "Bye"]
```
Running:
```bash
docker run myimg
```
Output:
```
Bye
```

### CMD + ENTRYPOINT Together
- Common pattern: **ENTRYPOINT** defines the fixed executable, **CMD** defines default arguments.

**Example:**
```dockerfile
FROM alpine
ENTRYPOINT ["echo"]
CMD ["Hello World"]
```
```bash
docker run myimg              # Hello World
docker run myimg "Bye World"  # Bye World
```

### Key Points
- ✔ Multiple CMD or ENTRYPOINT instructions are allowed, but **last one wins**.
- ✔ Use ENTRYPOINT for the main executable and CMD for default parameters.
- ❌ Avoid duplicating the same command in both, as it may cause repetition or unexpected results.
