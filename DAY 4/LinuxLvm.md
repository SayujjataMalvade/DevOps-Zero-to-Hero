# EC2 SSH Connection and Linux Disk & LVM Management Guide

This document provides a complete, professional, and structured guide
for:

-   Connecting to AWS EC2 instances from Windows
-   Managing Linux disks
-   Working with LVM (Logical Volume Manager) including creating,
    formatting, mounting, and verifying logical volumes

------------------------------------------------------------------------

# 📌 Prerequisites

Before executing the commands, ensure that:

1.  You have at least **one running EC2 instance** (e.g., Server).
2.  You can connect via **MobaXterm**, **Git Bash**, or **Windows CMD**
    using the `.pem` key.

------------------------------------------------------------------------

# 🔐 1. EC2 SSH Connection from Windows

### **Theory**

To access an EC2 instance, we use SSH (Secure Shell). On Windows, tools
like MobaXterm, PuTTY, or Git Bash allow secure remote login using a
private key file (.pem).

### **Command (Git Bash / MobaXterm Terminal)**

``` bash
ssh -i "your-key.pem" ec2-user@<EC2_Public_IP>
```

------------------------------------------------------------------------

# 💽 2. Disk and LVM Management in Linux

Linux storage is managed through:

-   **Block devices** (`/dev/xvda`, `/dev/xvdb`, etc.)
-   **LVM Components**
    -   *Physical Volume (PV)*
    -   *Volume Group (VG)*
    -   *Logical Volume (LV)*

LVM allows flexible disk management---expanding storage without
downtime.

------------------------------------------------------------------------

# 📍 Step-by-Step Commands

------------------------------------------------------------------------

## **1. View Available Block Devices**

### **Theory**

`lsblk` displays all attached block devices and their mount points.

### **Command**

``` bash
lsblk
```

------------------------------------------------------------------------

## **2. Create a Mount Point for Logical Volume**

### **Theory**

A mount point is an empty directory where a device will be attached.

### **Command**

``` bash
mkdir /mnt/sam_lv_mount
```

------------------------------------------------------------------------

## **3. Format Logical Volume with EXT4**

### **Theory**

Formatting converts the LV into a usable filesystem.

### **Command**

``` bash
mkfs.ext4 /dev/test_vg/demo_lv
```

------------------------------------------------------------------------

## **4. Mount the Logical Volume**

### **Theory**

Mounting attaches the LV to a directory so you can store files.

### **Command**

``` bash
mount /dev/test_vg/demo_lv /mnt/sam_lv_mount
```

------------------------------------------------------------------------

## **5. Create Directory and File Inside the Mounted Volume**

### **Commands**

``` bash
cd /mnt/sam_lv_mount/
mkdir devops
vim demo.txt
```

To view file contents:

``` bash
cat /mnt/sam_lv_mount/devops/demo.txt
```

------------------------------------------------------------------------

## **6. Unmount and Remount Logical Volume**

### **Theory**

Unmounting detaches the filesystem safely.

### **Commands**

``` bash
umount /mnt/sam_lv_mount/
mount /dev/test_vg/demo_lv /mnt/sam_lv_mount
```

------------------------------------------------------------------------

## **7. Mount a New Disk**

### **Theory**

A new EBS volume must be formatted and mounted before use.

### **Commands**

``` bash
mkdir /mnt/sam_disk_mount
mkfs -t ext4 /dev/xvdh
mount /dev/xvdh /mnt/sam_disk_mount/
```

------------------------------------------------------------------------

## **8. Check Disk Usage**

### **Theory**

`df -h` displays filesystem size, usage, and mount points.

### **Command**

``` bash
df -h
```

------------------------------------------------------------------------

# ✅ Outcome

After completing these steps:

1.  Logical volumes and disks are **properly formatted and mounted**.
2.  You can create, edit, and manage files inside mounted volumes.
3.  Both LVM-based storage and standalone disks are fully operational.

------------------------------------------------------------------------

# 📁 Summary

| Task            | Command                                          |
|-----------------|--------------------------------------------------|
| View disks      | `lsblk`                                          |
| Format LV       | `mkfs.ext4 /dev/test_vg/demo_lv`                 |
| Mount LV        | `mount /dev/test_vg/demo_lv /mnt/sam_lv_mount`   |
| Format new disk | `mkfs -t ext4 /dev/xvdh`                         |
| Mount new disk  | `mount /dev/xvdh /mnt/sam_disk_mount/`           |
| Check usage     | `df -h`                                          |




