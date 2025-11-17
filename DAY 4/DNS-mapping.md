# Commands and Explanations

This README provides a professional and detailed overview of commonly
used Linux/Unix commands along with their theoretical background and
practical usage.

## 1. `cat /etc/hosts`

### **Purpose**

The `cat /etc/hosts` command displays the contents of the `/etc/hosts`
file.

### **Theory**

The `/etc/hosts` file is a fundamental part of the local host name
resolution process in Unix-like systems.
Before DNS (Domain Name System) is queried, the system checks this file
to resolve hostnames to IP addresses.
It acts as a static, local database of hostnames---useful for overriding
DNS entries, creating local aliases, or defining internal network
mappings.

### **Use Cases**

-   Mapping custom domain names to local IPs
-   Testing websites before DNS propagation
-   Ensuring internal services resolve correctly
-   Blocking certain domains (e.g., ad servers)

### **Example**

``` bash
cat /etc/hosts
```

### **Typical Output**

    127.0.0.1   localhost
    ::1         localhost
    192.168.1.20   internal-server

------------------------------------------------------------------------


