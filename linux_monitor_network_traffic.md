# How to Monitor Network Traffic on Linux

## 1. `iftop` — Real-time Bandwidth Monitoring Per Connection

**Use Case:** View which remote hosts are consuming bandwidth in real-time.

**Install:**

```bash
sudo apt install iftop
```

**Usage:**

```bash
sudo iftop -i eth0         # Replace eth0 with your network interface
```

**Key Features:**

* Shows top connections by bandwidth
* Inbound/outbound traffic

**Tips:**

* Press `t` to toggle display modes
* Press `p` to pause
* Combine with `-B` for display in bytes

---

## 2. `nload` — Simple Interface Bandwidth

**Use Case:** Monitor incoming/outgoing traffic per interface.

**Install:**

```bash
sudo apt install nload
```

**Usage:**

```bash
sudo nload eth0
```

**Key Features:**

* Graphical view of upload/download rate
* Totals and current stats

---

## 3. `bmon` — Bandwidth Monitoring and Visualization

**Use Case:** Visual tool to monitor all interfaces and track traffic.

**Install:**

```bash
sudo apt install bmon
```

**Usage:**

```bash
sudo bmon
```

**Key Features:**

* Auto-detects interfaces
* Live graphs and rate history

---

## 4. `tcpdump` — Deep Packet Inspection

**Use Case:** Capture and inspect packets on an interface.

**Install:**

```bash
sudo apt install tcpdump
```

**Usage:**

```bash
sudo tcpdump -i eth0
```

**Example:**

```bash
sudo tcpdump -i eth0 port 80  # Capture only HTTP traffic
```

**Tips:**

* Use `-w` to save packets to file
* Analyze with Wireshark: `tcpdump -w capture.pcap`

---

## 5. `netstat` / `ss` — Network Connection Stats

**Use Case:** List active connections, ports, and listening services.

**Usage:**

```bash
ss -tulwn           # Faster replacement for netstat
```

**Example Output:**

* `t` – TCP
* `u` – UDP
* `l` – Listening
* `w` – Raw sockets
* `n` – Numeric output

**Bonus:** Use `ss -p` to see which process owns a port.

---

## 6. `nethogs` — Bandwidth by Process

**Use Case:** Identify processes using the most bandwidth.

**Install:**

```bash
sudo apt install nethogs
```

**Usage:**

```bash
sudo nethogs eth0
```

**Features:**

* Lists per-process bandwidth usage
* Real-time updates

---

## 7. `vnstat` — Long-term Network Usage Stats

**Use Case:** Track data usage over time (hourly/daily/monthly).

**Install:**

```bash
sudo apt install vnstat
sudo vnstat -u -i eth0
```

**Usage:**

```bash
vnstat                # Summary of usage
vnstat -d             # Daily usage
vnstat -m             # Monthly usage
```

**Great For:**

* Auditing bandwidth
* Avoiding data cap overages

---

## Best Practices & Tips

* **Run tools with `sudo`** to ensure full interface access
* **Know your interface name**: Use `ip a` to list interfaces
* **Combine tools**: Use `vnstat` for history, `iftop` for live monitoring
---
If the article helps you, leave a like, follow, or anything 🙂.

You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

  

**Bye**
---