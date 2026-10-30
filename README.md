# CHINENYEPRECIOUS-B084-WK1-PM1 — Cybersecurity Lab Setup: VirtualBox and Kali Linux

**Project Category:** Cybersecurity | Virtualization | Linux | Ethical Hacking  
**Difficulty:** Beginner  
**Status:** Kali Linux starts successfully, and internet access works.

## Project Overview

This project documents the preparation and configuration of a cybersecurity learning environment using Oracle VirtualBox and Kali Linux.

The purpose of this project is to establish a virtual environment where I can practise Linux administration, explore cybersecurity tools, perform security experiments, and develop practical skills in ethical hacking.

The project includes virtual machine configuration, memory allocation, display settings, network configuration, ISO selection, and testing of the Kali Linux environment.

## Project Objectives

- Set up a virtual cybersecurity laboratory.
- Configure a Kali Linux virtual machine.
- Understand virtual machine hardware settings.
- Configure network connectivity.
- Verify that Kali Linux boots successfully.
- Test internet connectivity.
- Document the setup process using screenshots.
- Prepare an environment for future cybersecurity and penetration-testing labs.

## Tools and Technologies

| Tool | Purpose |
|---|---|
| Windows 10/11 | Host operating system |
| Oracle VirtualBox | Virtualization platform |
| Kali Linux | Linux-based penetration-testing operating system |
| Kali Linux ISO | Operating system installation image |
| GitHub | Project documentation and version control |

## Virtual Machine Configuration

The following settings were reviewed during the project:

- **Operating System:** Linux
- **Distribution:** Debian
- **Version:** Debian (64-bit)
- **Allocated RAM:** 4096 MB (4 GB)
- **Graphics Controller:** VMSVGA
- **Video Memory:** 16 MB
- **Network Adapter:** Adapter 1
- **Network Mode:** NAT Network
- **Network Name:** NATNETWORK

## Installation and Configuration Process

### 1. VirtualBox General Settings

The virtual machine was configured with Linux as the operating system type and Debian (64-bit) as the version.

![Kali General Settings](screenshots/01-kali-general-settings.png)

### 2. System Configuration

The virtual machine was allocated 4096 MB of RAM to support the Kali Linux environment.

![Kali System Settings](screenshots/02-kali-system-settings.png)

### 3. Display Configuration

The display settings were reviewed, including the VMSVGA graphics controller and 16 MB of video memory.

![Kali Display Settings](screenshots/03-kali-display-settings.png)

### 4. Network Configuration

Adapter 1 was enabled and configured to use NAT Network with the network name NATNETWORK.

![Kali Network Settings](screenshots/04-kali-network-settings.png)

### 5. Creating the Virtual Machine

The initial virtual machine creation screen was reviewed before completing the required configuration details.

![New Virtual Machine](screenshots/05-new-vm-before-configuration.png)

### 6. Selecting the Kali Linux ISO

The Kali Linux installer ISO was selected:

`kali-linux-2025.3-installer-amd64.iso`

The virtual machine was configured to use Linux, Debian, and Debian (64-bit).

![Kali ISO Configuration](screenshots/06-kali-iso-vm-configuration.png)

### 7. VirtualBox Manager

The VirtualBox Manager was used to review the available virtual machines, including Kali, Parrot OS, and Windows 10.

![VirtualBox Manager](screenshots/07-virtualbox-manager-kali-vms.png)

### 8. VirtualBox Home Screen

The VirtualBox home screen provides access to creating, opening, and importing virtual machines.

![VirtualBox Home](screenshots/08-virtualbox-manager-home.png)

## Testing and Verification

After configuration, I confirmed that:

- Kali Linux starts successfully.
- Internet access is working.
- The virtual machine is ready for further cybersecurity practice.

The following Linux commands can be used to document network configuration and connectivity:

**Check network interfaces:**

```bash
ip address
```

**Check the routing table:**

```bash
ip route
```

**Test internet connectivity:**

```bash
ping -c 4 1.1.1.1
```

**Test DNS resolution:**

```bash
getent hosts kali.org
```

These commands can provide additional evidence of the working network environment.

## Troubleshooting and Lessons Learned

During this project, I developed a better understanding of:

- Virtual machine configuration.
- RAM allocation and system resources.
- Virtual network adapter settings.
- NAT Network configuration.
- Selecting an operating system ISO.
- The relationship between a host operating system and a guest operating system.

I also learned the importance of checking network configuration when troubleshooting connectivity problems in virtual environments.

## Project Status

- [x] VirtualBox configured.
- [x] Kali Linux virtual machine configured.
- [x] Kali Linux ISO selected.
- [x] Memory and display settings reviewed.
- [x] Network adapter configured.
- [x] Kali Linux boots successfully.
- [x] Internet connectivity confirmed.
- [ ] Additional terminal screenshots to be added.
- [ ] Further cybersecurity practical exercises to be documented.

## Future Improvements

The next stage of this project will involve:

- Installing and exploring cybersecurity tools.
- Practising Linux commands.
- Performing basic network reconnaissance in authorised lab environments.
- Conducting vulnerability assessment exercises.
- Documenting practical cybersecurity projects.

## Safety and Ethical Considerations

All cybersecurity activities carried out in this laboratory are intended for educational purposes and authorised testing only. Testing will be restricted to systems that I own or have explicit permission to assess.

## Official Resources

- [Oracle VirtualBox](https://www.virtualbox.org/)
- [Kali Linux](https://www.kali.org/)
- [Kali Linux Documentation](https://www.kali.org/docs/)
- [Kali Linux Downloads](https://www.kali.org/get-kali/)

## Author

**Chinenye Precious Ubosi**

**Project:** Cybersecurity Lab Setup – VirtualBox and Kali Linux  
**Project ID:** CHINENYEPRECIOUS-B084-WK1-PM1

**Technologies:** Windows | Oracle VirtualBox | Kali Linux | GitHub
