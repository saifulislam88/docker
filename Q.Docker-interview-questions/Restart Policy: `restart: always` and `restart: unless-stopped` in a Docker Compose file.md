
## What’s the difference between `restart: always` and `restart: unless-stopped` in Docker Compose❓

---

### 🔁 `restart: always`

- 🔄 **Always restarts** on failure or daemon reboot
- 💡 Even restarts after `docker stop`
- ✅ Best for: **critical services**, production uptime

```yaml
restart: always
```

| Condition              | Will Restart? |
|------------------------|---------------|
| Container crash        | ✅ Yes         |
| Docker reboot          | ✅ Yes         |
| Manual stop (`stop`)   | 🔁 Yes         |

---

### 🟡 `restart: unless-stopped`

- 🔄 Restarts unless **you stop it manually**
- ❌ **Won’t restart** after manual stop, even on reboot
- ✅ Best for: **semi-managed services**, dev/test

```yaml
restart: unless-stopped
```

| Condition              | Will Restart? |
|------------------------|---------------|
| Container crash        | ✅ Yes         |
| Docker reboot          | ✅ Yes         |
| Manual stop (`stop`)   | ❌ No          |

---

### 🔍 Summary

| Aspect               | `always`         | `unless-stopped`    |
|----------------------|------------------|----------------------|
| Crash recovery       | ✅ Yes           | ✅ Yes               |
| Docker reboot        | ✅ Yes           | ✅ Yes               |
| Manual stop persists | ❌ No            | ✅ Yes               |
| Use case             | Critical systems | Semi-managed apps   |

