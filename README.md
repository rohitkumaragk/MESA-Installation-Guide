# MESA-Installation-Guide
Complete MESA (Modules for Experiments in Stellar Astrophysics) installation guide for Linux with SDK setup
# 🌟 MESA Installation Guide for Linux

> Complete step-by-step guide to install MESA (Modules for Experiments in Stellar Astrophysics) on Linux systems

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![MESA Version](https://img.shields.io/badge/MESA-26.04.1-blue)](https://zenodo.org/records/19722306)
[![SDK Version](https://img.shields.io/badge/SDK-26.3.2-green)](http://user.astro.wisc.edu/~townsend/static.php?ref=mesasdk)

---

## 📋 Prerequisites

Before starting, ensure you have:
- Linux OS (Ubuntu/Debian/Fedora/CentOS recommended)
- Internet connection
- Minimum 5GB free disk space
- `wget`, `curl`, `unzip` installed

```bash
# Install required tools (Ubuntu/Debian)
sudo apt update
sudo apt install wget curl unzip build-essential -y

# For Fedora/RHEL/CentOS
sudo dnf install wget curl unzip gcc gcc-c++ make -y
