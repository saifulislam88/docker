### Why does containerd get installed automatically with Docker? What’s their relationship?

Docker depends on `containerd` to manage the container lifecycle. When Docker is installed, it includes Docker CLI, Docker Daemon (`dockerd`), containerd (runtime), and runc (low-level runtime).  
`Docker CLI → dockerd → containerd → runc → Linux Kernel`. Docker was modularized for better maintainability and CNCF compliance.
