# ElevateLabs_CS_Task08
Working with VPNs
# Task 8 — Working with VPNs (ProtonVPN / Windscribe)

## Objective
Install and test a free VPN client, verify IP/address changes, compare speed, and document privacy features and limitations.

## What I did
1. Signed up for a free ProtonVPN account (or Windscribe).
2. Installed the Linux client on Kali (or Windows app).
   - ProtonVPN (Linux): downloaded repo package, installed repo, and installed `proton-vpn-gnome-desktop`. See `reports/vpn_install_commands.txt`.
   - Windscribe (Linux): added Windscribe repo and installed `windscribe-cli`.
3. Connected to a VPN server (nearest/fastest).
4. Verified public IP change using `curl ipinfo.io/ip`.
5. Ran speed tests before and during VPN (`speedtest-cli`).
6. Performed DNS leak check via browser.
7. Saved screenshots and wrote `reports/report.md`.

## Commands used (examples)
```bash
# ProtonVPN (example)
wget https://repo.protonvpn.com/debian/dists/stable/main/binary-all/protonvpn-stable-release_1.0.8_all.deb
sudo dpkg -i ./protonvpn-stable-release_1.0.8_all.deb && sudo apt update
sudo apt install -y proton-vpn-gnome-desktop
protonvpn-cli login <username>
protonvpn-cli connect
curl -s ipinfo.io/ip > reports/ip_after.txt

# Windscribe (example)
echo 'deb https://repo.windscribe.com/ubuntu/ bionic main' | sudo tee /etc/apt/sources.list.d/windscribe-repo.list
sudo apt update
sudo apt install -y windscribe-cli
windscribe login
windscribe connect
curl -s ipinfo.io/ip > reports/ip_after_windscribe.txt
