# 🔁 Kali Linux NAT & IP Forwarding Script (2-VM Lab Setup)

This project provides a beginner-friendly Bash script to turn your **Kali Linux machine into a simple router** for a lab setup using **two VMnet interfaces**. This allows your internal VMs to access the internet **through Kali**, which acts as a bridge between them and your main network.

---

## 🛠️ What This Script Does

1. **Enables IP forwarding** so Kali can route packets between interfaces.
2. **Sets up NAT (masquerading)** on `eth2` (your internet-connected interface).
3. **Allows traffic forwarding** from:
   - `vmnet1` → `eth2`
   - `vmnet2` → `eth2`
4. **Saves iptables rules** so they persist across reboots.

---

## ⚙️ Network Interface Assumptions

This script assumes:
- `eth2` = your **internet-facing interface** (connected to NAT or bridged mode)
- `vmnet1` = first internal VM interface, where your **Windows victim (Active Directory server)** is connected
- `vmnet2` = second internal VM interface, e.g., attacker VM or IDS/firewall VM

> 🔧 **Tip:** You can modify the interface names inside the script (`kali_router_setup.sh`) to match your system. Use `ip a` to check your interface names.

---

## 📂 Files

- `setup_kali_gateway.sh` — Main setup script


