# Commands:
Network Interfaces: 
ifconfig -l

IP Address:
ipconfig getifaddr en0
networksetup -getinfo Ethernet

MAC address of the Wi-Fi card:
networksetup -getmacaddress Wi-Fi

Default Gateway:
route get default

NS lookup:
nslookup slash16.org