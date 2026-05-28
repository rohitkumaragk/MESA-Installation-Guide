# MESA-Installation-Guide
Complete MESA (Modules for Experiments in Stellar Astrophysics) installation guide for Linux with SDK setup

---

```markdown
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
```

---

## 🚀 Installation Steps

### Step 1: Create Project Folder

```bash
mkdir -p ~/MESA_Project
cd ~/MESA_Project
```

### Step 2: Download MESA SDK

Download the SDK from [official page](http://user.astro.wisc.edu/~townsend/static.php?ref=mesasdk):

```bash
wget https://user.astro.wisc.edu/~townsend/resource/download/mesasdk/x86_64-linux/mesasdk-x86_64-linux-26.3.2.tar.gz
```

> **Alternative:** Manual download from [http://user.astro.wisc.edu/~townsend/static.php?ref=mesasdk](http://user.astro.wisc.edu/~townsend/static.php?ref=mesasdk)

### Step 3: Extract SDK

```bash
tar -xvzf mesasdk-x86_64-linux-26.3.2.tar.gz
```

This creates a `mesasdk` folder.

### Step 4: Set SDK Path

> ⚠️ **Important:** Replace `/home/rahul` with your actual username

```bash
# Using full path (RECOMMENDED - avoids confusion)
export MESASDK_ROOT=/home/$USER/MESA_Project/mesasdk

# Verify the path
echo $MESASDK_ROOT
```

**Understanding `~` (Home Directory):**
- `~` means home directory
- If username is `rahul`: `~/mesasdk` = `/home/rahul/mesasdk`

### Step 5: Initialize SDK

```bash
source $MESASDK_ROOT/bin/mesasdk_init.sh
```

> **Note:** This command produces no output normally - that's perfectly fine!

### Step 6: Verify SDK Installation

```bash
# Check gfortran location
which gfortran

# Check version
gfortran --version
```

**Expected Output:**
```
/home/username/MESA_Project/mesasdk/bin/gfortran
GNU Fortran (GCC) 15.2.0
```

### Step 7: Download MESA Source

```bash
# Download from Zenodo (~2.3 GB)
wget https://zenodo.org/records/19722306/files/mesa-26.04.1.zip

# Or use curl
curl -L -o mesa-26.04.1.zip https://zenodo.org/records/19722306/files/mesa-26.04.1.zip
```

### Step 8: Extract Source Code

```bash
unzip mesa-26.04.1.zip
cd mesa-26.04.1
```

### Step 9: Re-initialize SDK (Important!)

```bash
export MESASDK_ROOT=/home/$USER/MESA_Project/mesasdk
source $MESASDK_ROOT/bin/mesasdk_init.sh
```

### Step 10: Install MESA

```bash
./install
```

### Step 11: Wait for Completion

- ⏱️ **Minimum:** ~20 minutes
- ⏱️ **Maximum:** ~60 minutes
- Depends on your system performance

**Success Message:**
```
*************************************
*                                   *
*           successful!             *
*                                   *
*************************************
```

---

## 🔧 Post-Installation Setup

### Add to ~/.bashrc (Permanent Setup)

To avoid setting paths every time, add these lines to `~/.bashrc`:

```bash
echo '# MESA SDK Configuration' >> ~/.bashrc
echo 'export MESASDK_ROOT=/home/$USER/MESA_Project/mesasdk' >> ~/.bashrc
echo 'source $MESASDK_ROOT/bin/mesasdk_init.sh' >> ~/.bashrc
echo 'export MESA_DIR=/home/$USER/MESA_Project/mesa-26.04.1' >> ~/.bashrc
```

Then reload:
```bash
source ~/.bashrc
```

### Test MESA Installation

```bash
cd $MESA_DIR
./eos/test
./star/test
```

---

## ❗ Troubleshooting Common Issues

| Issue | Solution |
|-------|----------|
| `gfortran: command not found` | SDK not initialized properly. Run Step 4 & 5 again |
| Permission denied | Use `chmod +x install` or check folder permissions |
| Download fails | Use manual download from Zenodo |
| Build fails | Check disk space: `df -h` |

---

## 📦 Quick Command Summary

```bash
# Complete installation in one go (if files already downloaded)
export MESASDK_ROOT=/home/$USER/MESA_Project/mesasdk
source $MESASDK_ROOT/bin/mesasdk_init.sh
cd ~/MESA_Project/mesa-26.04.1
./install
```

---

## 📚 Resources

- [MESA Official Website](https://mesa.sourceforge.io/)
- [MESA SDK Download](http://user.astro.wisc.edu/~townsend/static.php?ref=mesasdk)
- [MESA Source on Zenodo](https://zenodo.org/records/19722306)
- [MESA Forum](https://groups.google.com/g/mesa-users)

---

## 🤝 Contributing

Found an issue? Have suggestions? Feel free to:
1. Open an Issue
2. Submit a Pull Request
3. Star ⭐ this repository if it helped!

---

## 📄 License

MIT License - feel free to use and share!

---

## ⭐ Support

If this guide helped you, please give it a star! ⭐

---

**Made with ❤️ for the astrophysics community**
```

---

## 📋 **Copy-Paste Instructions:**

1. **Is poori text ko copy karein** (upar wala sab kuch)
2. GitHub par apne repository mein **README.md** file open karein
3. **Edit button** (pencil icon) click karein
4. **Saara purana content delete karein** (Ctrl+A, then Delete)
5. **Naya content paste karein** (Ctrl+V)
6. Neeche scroll karein → **"Commit changes"** button click karein
7. Green button click karein → **"Commit changes"**

---

## ✅ **Done! Ab aapka README perfect hai!**

Bas itna karna hai! 🚀
