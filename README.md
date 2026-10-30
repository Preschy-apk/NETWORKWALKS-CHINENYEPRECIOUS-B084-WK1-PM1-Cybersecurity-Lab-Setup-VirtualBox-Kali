# CHINENYEPRECIOUS-B084-WK1-PM1 — Cybersecurity Lab Setup: VirtualBox and Kali Linux

**Project category:** Cybersecurity | Virtualization | Linux | Ethical Hacking  
**Difficulty:** Beginner  
**Status:** In progress — virtual machine configuration documented; successful Kali boot and network tests still need evidence.

## Project overview

This project documents the preparation of a virtual cybersecurity learning environment using Oracle VirtualBox on a Windows host and Kali Linux as the guest operating system. Virtualization makes it possible to practise Linux administration and future security exercises without replacing the host operating system.

The screenshots currently available show VirtualBox configuration screens, a Kali Linux installer ISO selected for a new virtual machine, and the VirtualBox Manager. They do **not yet show Kali successfully booted or network tests completing**, so those outcomes are left for later verification.

## Objectives

- Install and open Oracle VirtualBox on Windows.
- Select the official Kali Linux installer image.
- Create and configure a Kali Linux virtual machine.
- Review memory, display, storage, and networking settings.
- Complete the Kali installation and verify that it boots.
- Test IP configuration, routing, internet connectivity, and DNS.
- Document the process with authentic screenshots.
- Prepare a reusable lab for future authorised cybersecurity practice.

## Tools and technologies

| Tool | Purpose |
|---|---|
| Windows host | Runs VirtualBox |
| Oracle VirtualBox | Virtualization platform |
| Kali Linux installer ISO | Installs the guest operating system |
| Kali terminal | Network and system checks after installation |
| GitHub | Stores documentation and screenshots |

## Installation approach

The screenshots indicate that this project is using the **ISO installation method**, rather than importing a prebuilt Kali virtual machine. The ISO shown in the screenshot is named `kali-linux-2025.3-installer-amd64.iso`.

Official resources:
- [Oracle VirtualBox downloads](https://www.virtualbox.org/wiki/Downloads)
- [Kali Linux downloads](https://www.kali.org/get-kali/)
- [Kali Linux installation documentation](https://www.kali.org/docs/installation/)
- [Kali Linux VirtualBox documentation](https://www.kali.org/docs/virtualization/install-virtualbox-guest-vm/)

## Step 1 — Review the virtual machine identity and operating system

The General settings screenshot shows the VM name as `Kal`, with Linux selected, Debian as the distribution, and Debian (64-bit) as the version.

For a clearer project, rename the VM to **Kali Linux** or **kali-linux** before installation, if the VM is powered off. This is a display name and does not itself change the guest operating system.

![Kali general settings](screenshots/01-kali-general-settings.png)

*Figure 1. VirtualBox General settings for the Kali VM.*

## Step 2 — Review memory and boot settings

The System screenshot shows **4096 MB (4 GB) of base memory**. This is a reasonable starting allocation if the Windows host has sufficient RAM available. Keep enough memory for Windows and other running applications.

The screenshot also shows the boot-device order and other motherboard settings. For an ISO installation, the virtual optical drive must be available during the initial boot. After Kali is installed, the virtual hard disk should be used for normal startup.

![Kali system settings](screenshots/02-kali-system-settings.png)

*Figure 2. System settings, including 4096 MB of allocated memory.*

## Step 3 — Review display settings

The Display screenshot shows 16 MB of video memory and the VMSVGA graphics controller. Once the guest operating system is installed, if the display is too small or performs poorly, shut down the VM and review the display settings. Increase video memory where VirtualBox permits and the host has adequate resources. Do not enable 3D acceleration unless needed for troubleshooting or performance.

![Kali display settings](screenshots/03-kali-display-settings.png)

*Figure 3. Virtual display configuration before the first successful boot.*

## Step 4 — Review the virtual network adapter

The Network screenshot shows Adapter 1 enabled and attached to **NAT Network**, with the network named `NATNETWORK` and “Virtual Cable Connected” selected.

NAT Network is a valid option when configured correctly, especially if multiple VMs need to share the same NAT network. It is not the same as the simpler **NAT** mode. Before troubleshooting internet access, confirm that the NAT network named `NATNETWORK` exists and is started in VirtualBox's network settings. If you only need internet access from one VM, you can also use **NAT** as a simpler initial test.

![Kali network settings](screenshots/04-kali-network-settings.png)

*Figure 4. Adapter 1 is enabled and attached to the NAT Network named NATNETWORK.*

## Step 5 — Create a new virtual machine

The New Virtual Machine screenshot first shows an incomplete form with the VM name missing. That is an initial setup screen, not a completed installation. The next screenshot shows the form filled in with `kali-linux`, the Kali installer ISO, Linux, Debian, and Debian (64-bit).

![New VM form before configuration](screenshots/05-new-vm-before-configuration.png)

*Figure 5. Initial New Virtual Machine screen before the required fields were completed.*

## Step 6 — Select the Kali installer ISO

The configured VM form shows:
- VM name: `kali-linux`
- ISO image: `kali-linux-2025.3-installer-amd64.iso`
- OS: Linux
- Distribution: Debian
- Version: Debian (64-bit)
- Unattended installation: not selected

Leaving unattended installation unchecked allows you to proceed through the Kali installer manually, following its prompts for language, location, keyboard, account, time zone, disk setup, software, and bootloader as applicable.

Before clicking **Finish**, expand the hardware and virtual hard disk sections and review the proposed memory, CPU, and disk allocation. Make sure the virtual disk has sufficient capacity and that you have selected the intended ISO.

![Kali ISO VM configuration](screenshots/06-kali-iso-vm-configuration.png)

*Figure 6. Kali installer ISO selected in the New Virtual Machine wizard.*

## Step 7 — Check VirtualBox Manager

The VirtualBox Manager screenshot shows entries named `Kal`, `Parrot os`, and `windows 10`, all powered off. This confirms that VirtualBox Manager lists these VMs; it does not prove that Kali has booted successfully.

![VirtualBox Manager with VMs](screenshots/07-virtualbox-manager-kali-vms.png)

*Figure 7. VirtualBox Manager listing the configured virtual machines.*

A second screenshot shows the VirtualBox Manager home screen with options to create, open, or import a virtual machine.

![VirtualBox Manager home](screenshots/08-virtualbox-manager-home.png)

*Figure 8. VirtualBox Manager home screen.*

## Step 8 — Complete the Kali installation

This step still needs to be performed and documented:

1. Select `kali-linux` in VirtualBox Manager.
2. Click **Start**.
3. When the Kali boot menu appears, select the graphical installer (if offered).
4. Follow the installer prompts carefully.
5. When partitioning, ensure changes apply to the VM's virtual disk, not the Windows host disk.
6. Complete installation and install the bootloader when prompted.
7. Restart the VM.
8. If it returns to the installer, detach the ISO from the virtual optical drive and boot from the virtual hard disk.
9. Sign in with the account credentials created during installation.

**Screenshot to add:** `09-kali-installer.png` — capture a relevant installer screen.  
**Screenshot to add:** `10-kali-desktop.png` — capture the Kali desktop after a successful boot.

## Step 9 — Verify network configuration

After Kali boots, open Terminal and run:

```bash
ip address
```

This displays network interfaces and assigned addresses. Then run:

```bash
ip route
```

Check whether a default route exists. Record the actual output rather than copying an example address from another machine.

**Screenshot to add:** `11-kali-ip-address.png`  
**Screenshot to add:** `12-kali-routing-table.png`

## Step 10 — Test connectivity and DNS

Test IP connectivity:

```bash
ping -c 4 1.1.1.1
```

Then test DNS resolution:

```bash
getent hosts kali.org
```

A failed ping does not automatically mean the VM has no internet access, because ICMP may be filtered. Interpret the results alongside the route, DNS lookup, and other connectivity checks.

**Screenshot to add:** `13-kali-connectivity-test.png`  
**Screenshot to add:** `14-kali-dns-test.png`

## Troubleshooting notes

If the VM does not start or has no network access:

- Record the exact error message.
- Confirm the VM has adequate RAM, CPU, and virtual disk space.
- Confirm the Kali ISO is attached during installation.
- For NAT Network, confirm `NATNETWORK` exists and is running.
- Check `ip address` and `ip route` inside Kali.
- Change one setting at a time and repeat the test.

Add only troubleshooting steps and outcomes that you actually experienced.

## Current status and next steps

- [x] VirtualBox Manager opened.
- [x] Kali VM settings reviewed.
- [x] Kali installer ISO selected in the VM wizard.
- [x] Memory, display, and network settings captured.
- [ ] Finish VM creation and complete Kali installation.
- [ ] Capture successful Kali desktop.
- [ ] Test IP configuration, routing, connectivity, and DNS.
- [ ] Record actual test results and any troubleshooting.
- [ ] Update project status to Completed only after verification.

## Safety and ethical use

This lab is for learning and authorised security testing. Only test systems you own or have explicit permission to assess. Keep vulnerable test systems isolated from untrusted networks.

## Project details

**Author:** Chinenye Precious Ubosi  
**Project ID:** CHINENYEPRECIOUS-B084-WK1-PM1  
**Platform:** Windows + Oracle VirtualBox + Kali Linux  
**Project type:** Hands-on cybersecurity lab setup
