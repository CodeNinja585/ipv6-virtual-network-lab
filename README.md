
# 🚀 IPv6-Only Virtual Network Lab Using Cisco Packet Tracer

## 📘 Overview

This project simulates an IPv6-only home/virtual network using **Cisco Packet Tracer**. It demonstrates how IPv6 devices use **SLAAC** to autoconfigure addresses, how static addressing is applied for servers, and how all nodes communicate via an IPv6-configured router.

## 🎯 Objectives

- Set up IPv6-only communication without relying on IPv4
- Use SLAAC for PC autoconfiguration
- Manually configure a static IPv6 for a server
- Validate end-to-end connectivity across devices
- Practice CLI interaction and IPv6 interface setup

---

## 🖥️ Lab Topology

```

\[PC0]     \[PC1]     \[PC2]
\        |         /
\[Switch]——\[Server]

\[Router]

```

### Devices:
- 1x Router
- 1x Switch
- 3x PCs (SLAAC)
- 1x Server (static IPv6)

---

## ⚙️ Configuration Summary

| Device | IPv6 Address                  | Gateway                    | Notes                         |
|--------|-------------------------------|----------------------------|-------------------------------|
| Router | `2001:db8:acad:1::1/64`       | —                          | Sends RA for SLAAC           |
| Server | `2001:db8:acad:1::5/64`       | `2001:db8:acad:1::1`       | Static IP manually configured|
| PC0    | SLAAC                         | Via Router RA              | Auto-configured              |
| PC1    | SLAAC                         | Via Router RA              | Auto-configured              |
| PC2    | SLAAC                         | Via Router RA              | Auto-configured              |

---

## 🧪 Testing & Validation

All of the following were tested and successful:

- ✅ PCs received SLAAC addresses
- ✅ Server configured manually and reachable
- ✅ Router was reachable from all nodes
- ✅ All devices could ping each other over IPv6

---

## 📁 Repository Structure

```

📦 campus-ipv6-network/
├── README.md
└── artifacts/
├── configs/
│   ├── router\_ipv6\_config.txt
│   └── switch\_fa0\_5\_config.txt
├── screenshots/
│   └── \[captures of PC/server/CLI/ping tests]
└── topology/
├── ipv6-lab-diagram.png
└── ipv6-network.pkt

```

---

## 📸 Screenshots

- IPv6 address on each PC
- Ping tests (router <--> server, PC <--> PC)
- Router & switch CLI command outputs
- Static IP config on server

---

## 🧠 What I Learned

- How SLAAC works and depends on router advertisements
- How to manually configure static IPv6 on servers
- Importance of matching subnet prefixes
- Verifying and debugging connectivity in IPv6-only networks

---

## ⚠️ Challenges Faced

### 🔸 Issue: Server unreachable
**Cause:** Wrong IPv6 gateway (`2001:db8:acad::1`) was used instead of `2001:db8:acad:1::1`.

**Fix:** Corrected the router's address and reconfigured the server gateway.

### 🔸 Issue: SLAAC not working
**Cause:** Router interface was either down or lacked `ipv6 enable`.

**Fix:** Enabled interface and configured IPv6 address and `ipv6 enable`.

---

## 📦 Resources

- `.pkt` file included for replication
- `.txt` CLI logs included for reference
- Screenshots in `/artifacts/screenshots`

---

## 🔗 Author

**Donald Likke**  
Project built with 💻 and documented for hands-on networking growth.  
[GitHub](https://github.com/CodeNinja585) | [LinkedIn](https://www.linkedin.com/in/donald-okputu-b7b431290/)

---

> If this helped you, drop a ⭐️ on the repo or fork and try it yourself!
```
