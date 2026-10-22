<p align="center">
  <img src="assets/logo.png" alt="Catana Logo" width="200"/>
</p>


# catana
Catana is an interactive Pentest Team bootstrapper for Kali Linux, originally inspired by PimpMyKali, but tailored to the tooling needs of our Penetration Testing team when we boot up a fresh VM. It automates the installation and setup of essential offensive security tools, environments and configurations.

## Features

**System Setup & Configuration**
- System update and upgrade
- Docker & Docker Compose installation and validation

**Environment Bootstrapping**
- Python 3 virtual environment creation
- Pip upgrade within venv
- Auto-unzipping of the rockyou.txt wordlist
- Adds GOPATH and Go-based tooling setup

**Core Tools Installation**
- Common tools:  
  - nmap, jq, gcc, gedit, proxychains4, rlwrap, ncat, remmina, filezilla
- Other essentials:
  - impacket (via pip in venv)
  - PEASS-ng suite (cloned to /opt/PEASS-ng)
  - BloodHound backend via Docker in a dedicated tmux session

**Recon Tools**
- nuclei for vulnerability scanning
- subfinder, github-subdomains, assetfinder, sublist3r, dnsx, httpx for subdomain and asset enumeration
- feroxbuster for content discovery

**Frontend Security Tools**
- Node.js tools such as:
  - js-beautify (via npm)
  - sourcemapper (via Go)

## Requirements

- Root privileges (sudo)
- Internet connection
- Standard CLI tools: apt, bash, git, etc.

## Installation

### 1. Clone the repo and change directory
```bash
git clone https://github.com/ljoer/catana.git
cd catana
```
### 2. Run the installer for the first time
```bash
sudo bash ./catana.sh
```
### 3. From now on you can run catana directly
```bash
sudo catana
```
---
#### To pull in updates and reinstall system-wide:
```bash
cd catana
git pull https://github.com/ljoer/catana.git
```
- Re-run the installer script to update /usr/local/bin/catana
```bash
sudo bash ./catana.sh
```
## Disclaimer

Catana is intended for educational and authorized penetration testing use only. Always obtain proper permission before using tools that interact with or scan remote systems.

