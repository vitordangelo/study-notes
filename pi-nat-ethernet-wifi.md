https://pimylifeup.com/raspberry-pi-wifi-bridge/

# Share WiFi With Ethernet Port on a Raspberry Pi

## 1. Install dnsmasq

```sh
sudo apt-get install dnsmasq -y
```

## 2. Configure the eth0

> sudo vim /etc/dhcpcd.conf

Edit the eth0 section like this:

```sh
interface eth0
static ip_address=192.168.2.10/24
static routers=192.168.2.1
static domain_name_server 1.1.1.1
```

## 3. Config the dnsmasq

**Backup file before:**

```sh
sudo mv /etc/dnsmasq.conf /etc/dnsmasq.conf.orig
```

> sudo vim /etc/dnsmasq.conf

**Paste the following into the new file:**

```sh
interface=eth0      # Use interface eth0
listen-address=192.168.2.1 # listen on
# Bind to the interface to make sure we aren't sending things
# elsewhere
bind-interfaces
server=8.8.8.8       # Forward DNS requests to Google DNS
domain-needed        # Don't forward short names
# Never forward addresses in the non-routed address spaces.
bogus-priv
# Assign IP addresses between 192.168.2.2 and 192.168.2.100 with a
# 12 hour lease time
dhcp-range=192.168.2.2,192.168.2.100,12h
```

## 4. Edit the /etc/sysctl.conf file to enable packet forwarding

> sudo vim /etc/sysctl.conf

Remove the # from the beginning of the line containing **net.ipv4.ip_forward=1**
This will enable packet forwarding on next reboot. But if you want to try it right now without reboot then do this.

## 5 Config the IP Tables

