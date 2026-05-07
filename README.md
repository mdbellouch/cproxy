[README.md](https://github.com/user-attachments/files/27495920/README.md)
# 🌐 cproxy — Cosmic Proxy Manager

> A simple, colorful terminal tool to manage your system proxy on Linux (GNOME).


---

## ✨ Features

| Feature | Description |
|---|---|
| ⚡ Power On / Off  | Enable or disable your system proxy in one keystroke |
| 📊 Live Status   | See your current proxy type, host, and port at a glance |
| 🔧 Manual Setup   | Configure HTTP or SOCKS proxy with optional credentials |
| 💾 Save Profiles  | Save multiple proxy configs and switch between them easily |
| 📂 Load Profiles  | Apply a saved profile instantly |

---

## 🖥️ Requirements

- **OS:** Linux with a GNOME desktop environment (Ubuntu, Fedora, Pop!_OS, etc.)
- **Python:** 3.x (usually pre-installed)
- **Tools:** `gsettings` (comes with GNOME — no extra install needed)

> ⚠️ **Does not work on KDE, XFCE, or non-GNOME desktops.**

---

## 🚀 Installation

**1. Clone the repository:**
```bash
git clone https://github.com/mdbellouch/cproxy.git
cd cproxy
```

**2. Make the script executable:**
```bash
chmod +x cproxy
```

**3. Install globally so you can run it from anywhere:**
```bash
sudo cp cproxy /usr/local/bin/cproxy
```

---

## ▶️ Usage

```bash
# installed globally:
cproxy
```

You'll see the main menu. Just type the number for what you want to do:

```
[1] Power On       → Activates the configured proxy
[2] Power Off      → Disables the proxy
[3] Status         → Shows current proxy state and settings
[4] Manual Setup   → Enter host, port, type and optional credentials
[5] Save Profile   → Save a proxy config under a name
[6] Load Profile   → Pick and apply a previously saved config
[7] Exit           → Quit the tool
```

---

## 📖 Step-by-Step Examples

### Set up a proxy manually

1. Run `cproxy`
2. Press `4` for **Manual Setup**
3. Enter your proxy details:
   ```
   Host: 192.168.1.100
   Port: 8080
   Type (http/socks) [http]: http
   User: (leave blank if no auth needed)
   ```
4. The proxy is applied and turned on automatically ✅

---

### Save and reuse a proxy profile

1. Press `5` for **Save Profile**
2. Give it a name, e.g. `work-vpn`
3. Enter the proxy details
4. Next time, press `6` → **Load Profile** → select `work-vpn`

---

### Check if the proxy is active

Press `3` for **Status**. You'll see something like:

```
=== LIVE SYSTEM STATUS ===
State: [ ACTIVE ]
 >> HTTP:  192.168.1.100:8080
 >> SOCKS: (none)
```

---

## 📁 File Locations

| File | Purpose |
|---|---|
| `~/.config/cosmic-proxy/profiles.json` | Stores your saved proxy profiles |

> 🔒 The profiles file is saved with restricted permissions (`0600`) — only your user can read it.

---

## ⚠️ Known Limitations

- **GNOME only** — Uses `gsettings`, which is GNOME-specific.
- **Passwords stored in plaintext** — Proxy credentials in saved profiles are not encrypted. Avoid saving sensitive passwords on shared machines.
- **System proxy only** — Some apps (like terminal tools `curl`, `wget`, `git`) don't respect the GNOME system proxy. You may need to set `http_proxy` environment variables separately for those.

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or pull requests.

1. Fork the repo
2. Create your feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m 'Add my feature'`
4. Push to the branch: `git push origin feature/my-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Md BELLOUCH**
- GitHub: [@mdbellouch](https://github.com/mdbellouch)
- Instagram: [@s3j_.4](https://instagram.com/s3j_.4)

---

*If you find this tool useful, feel free to ⭐ star the repo!*
