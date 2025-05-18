# EvilTwin Phase 1 – Automated Setup Script

This is a Bash script that automates the setup of an EvilTwin Wi-Fi access point using:

- `airbase-ng` to broadcast a fake Wi-Fi network
- `dnsmasq` to provide DHCP and DNS
- `Wireshark` to capture traffic on the virtual at0 interface

It simplifies the first phase of EvilTwin attacks for use in labs, demonstrations, or red team environments.

## 🚀 Features

- Interactive SSID and channel input
- Cleans up conflicting processes
- Launches airbase-ng with your input
- Assigns IP and netmask to at0
- Restarts dnsmasq with your config
- Automatically opens Wireshark on `at0`

## 🧪 Usage

1. Make sure you have `aircrack-ng`, `dnsmasq`, and `Wireshark` installed
2. Create a dnsmasq config file at `/root/dnsmasq.conf` like the example below
3. Run the script:

```bash
chmod +x eviltwin-phase1.sh
sudo ./eviltwin-phase1.sh
```

You'll be prompted to enter the SSID and channel you want to spoof.

## 🧾 Example `/root/dnsmasq.conf`

```ini
interface=at0
dhcp-range=10.0.0.10,10.0.0.50,12h
dhcp-option=3,10.0.0.1
dhcp-option=6,8.8.8.8
log-queries
log-dhcp
```

## ⚠️ Disclaimer

This tool is for **educational and authorized testing purposes only**.  
Do not use it on networks you do not own or have explicit permission to test.  
The creator is not responsible for any misuse or damage caused.

## 🤝 Open to Suggestions

I'm always open to suggestions, improvements, or feedback.  
If you have ideas to enhance this script or want to collaborate on the next phase (like captive portal phishing), feel free to fork the repo or open an issue.

---

📌 Created by [Ahmed Abassam](https://github.com/Abassam08)
