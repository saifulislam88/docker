### Pi-hole Installation via docker-compose

```bash 
https://github.com/pi-hole/docker-pi-hole
```

- Disable Ubuntu Internal DNS (systemd-resolved)
  
```bash vim /etc/systemd/resolved.conf ```
`DNSStubListener=no`

```bash
echo -e "nameserver 8.8.8.8\nnameserver 1.1.1.1" | sudo tee /etc/resolv.conf
sudo systemctl restart systemd-resolved
sudo systemctl daemon-reexec
sudo systemctl restart systemd-resolved
```

```bash
services:
  pihole:
    container_name: pihole
    image: pihole/pihole:latest
    hostname: pihole.msi.com
    ports:
      - "53:53/tcp"
      - "53:53/udp"
      - "67:67/udp"         # DHCP (optional — disable if not using)
      - "8001:80/tcp"       # Web UI (http://localhost:8001/admin)

    environment:
      TZ: Asia/Dhaka
      DNSMASQ_USER: root     # Required for newer systems (avoids permission issues)
      FTLCONF_webserver_api_password: 'admin'
    volumes:
      - ./etc-pihole/:/etc/pihole/
      - ./etc-dnsmasq.d/:/etc/dnsmasq.d/

    restart: unless-stopped
```

- Manually reset password from inside container

```bash
docker exec -it pihole bash
pihole -a -p
```
- DNS Settings
http://172.30.0.234:8001/admin/
<img width="2502" height="1236" alt="image" src="https://github.com/user-attachments/assets/3e427761-3e17-42be-a3f8-4d5f034512bf" />


```bash
apt install bind9-dnsutils
dig google.com @127.0.0.1 -p 53
dig youtube.com @172.30.0.234 -p 53
```
