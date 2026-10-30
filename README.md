# NETWORKWALKS--EMMANUEL-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
Linux VM setup
# 🐉 Cybersecurity & Pentesting Lab Setup (VirtualBox + Kali Linux)

## 📖 Overview

A virtual cybersecurity lab built with **VirtualBox** and **Kali Linux** for my Ethical Hacking certificate. Kali runs on a private **NAT Network**, so more VMs (e.g. target machines) can be added later for authorized security testing.

> ⚠️ **Only test systems you own or have explicit permission to test.** This lab is for education only.

## 🎯 Objectives

- Install VirtualBox and import the Kali Linux VM
- Create a NAT Network and attach Kali to it
- Configure IPv4 settings and confirm internet and browsing work
- Create a clean snapshot for recovery

## ⚙️ Configuration

| Component | Setting |
|---|---|
| 🖥️ Host OS | Windows [10/11] |
| 🧰 Hypervisor | VirtualBox [version] |
| 🐉 Guest OS | Kali Linux [version] |
| 🧠 Kali RAM | [2048] MB |
| 🌐 Network | NAT Network (`NatNetwork`) |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP | 10.0.0.2/24 |
| 🚪 Gateway | 10.0.0.1 |
| 🌍 DNS | 8.8.8.8 |

## 🪜 Setup Steps

1. **Install 7-Zip and VirtualBox.** 7-Zip extracts the Kali VM archive.
2. **Create the NAT Network** in VirtualBox: name `NatNetwork`, prefix `10.0.0.0/24`, DHCP enabled.
   📸 `screenshots/01-nat-network.png`
3. **Import Kali Linux** (downloaded from the official Kali site) and set Adapter 1 to *NAT Network → NatNetwork*.
   📸 `screenshots/02-kali-adapter.png`
4. **Configure the IPv4 settings** on Kali: IP `10.0.0.2`, mask `255.255.255.0`, gateway `10.0.0.1`, DNS `8.8.8.8`.
   📸 `screenshots/03-ip-config.png`
5. **Verify connectivity and browsing** (see below).
   📸 `screenshots/04-browsing.png`
6. **Create a snapshot** named `Clean Kali - Network Setup` as the recovery baseline.
   📸 `screenshots/05-snapshot.png`

## 🔎 Verification

| Test | Command | Expected |
|---|---|---|
| IP address | `ip a` | `10.0.0.2/24` shown |
| Gateway | `ping 10.0.0.1` | Replies |
| Internet | `ping 8.8.8.8` | Replies |
| DNS | `nslookup google.com` | Resolves |
| Browsing | Open a site in Firefox | Page loads |
| Snapshot | Restore it, run `ip a` | Baseline restored |

## 🐞 Problem & Solution

**Problem:** I first tried to reuse a Linux VM I already had installed and attach it to this lab. It failed to load because of a **version mismatch**.

**Solution:** I downloaded the fresh Kali Linux VM image expected for this lab, imported it, and it worked straight away. Lesson: use the VM image the lab is built for instead of forcing an old VM into a new setup.

## 💡 What I Learned

- **NAT vs NAT Network:** a NAT Network lets VMs talk to each other *and* reach the internet, which a multi-VM lab needs.
- **VM networking:** how VirtualBox adapters connect VMs to networks.
- **IPv4 config:** setting and checking IP, mask, gateway and DNS on Kali.
- **Snapshots:** take a clean one before any risky work.
- **VM compatibility:** an existing VM may not load in a different VirtualBox setup, so a fresh image saves time.

## 🔗 Tools

- 7-Zip: https://7-zip.org/download.html
- VirtualBox: https://virtualbox.org/wiki/Downloads
- Kali Linux: https://kali.org/get-kali

## 👤 Author

**Phelele kwanele**, Ethical Hacking Certificate lab project
GitHub: [(https://github.com/PHELELEKE/NETWORKWALKS--EMMANUEL-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP)] · LinkedIn:(https://lnkd.in/p/dba3vkSH)
