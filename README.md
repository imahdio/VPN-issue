based [this youtube video](https://www.youtube.com/watch?v=H9157KFBPdc), I have setted up softether VPN server on my azure Ubuntu server.
I'm checking the results from 2 locations in every try:

1-my own PC connected to local restricted internet by ISP/government
2-remote USA based windows server

Here are the results:

## ▉ Open vpn connection
port|results
-|-
443 tcp|![openvpn03](https://user-images.githubusercontent.com/64577273/196978432-bc63737e-a7aa-442b-9877-7a15079a049c.jpg)
1194 udp|![openvpn02](https://user-images.githubusercontent.com/64577273/196978704-fad2fd73-95cb-44ef-9637-08d8d02e0503.jpg)
2626 udp|![openvpn01](https://user-images.githubusercontent.com/64577273/196978197-950e42bc-81db-4a1e-9eab-f3a58e240b6e.jpg)

Notice: as be shown in above table, the connection refused on my own local PC which is connected to restricted internet by ISP/government but that test passed from USA based server successfully.

## ▉ L2tp connection
this is the active L2tp vpn from my softether vpn server which is accessible even right now for your test:

details|results
-|-
ip: 20.150.215.135<br>type: L2TP/IPsec<br>PSK: vpn<br>username: user01<br>password: 20222022|![l2tp-default500and4500ports](https://user-images.githubusercontent.com/64577273/196980481-1284996d-51ec-41b7-a3c4-6e3bbf5e85ff.jpg)


notice: as be shown in above table, the connection refused on my own local PC which is connected to restricted internet by ISP/government but that test passed from USA based server successfully.

## ▉ Wireguard connection:
I've used [this script](https://github.com/Nyr/wireguard-install) for installing wireguard on my other ubuntu server without any results even with diffrent ports and dns servers as the open vpn tests.

details<br>it's available for your test right now|result on my local PC
-|-
[Interface]<br>Address = 10.7.0.2/24<br>DNS = 8.8.8.8, 8.8.4.4<br>PrivateKey = EPfUDRKTSvUkVL1joLB00CFEUr1yhy2okowqNyO11kQ=<br>MTU = 1380<br><br>[Peer]<br>PublicKey = GujR7NI78fkvXnY9xNINoInS6uoZIr1CzreSNUd6Pmk=<br>PresharedKey = ANmW3NDAwAVdkAVWoqcT+KRUlXYOKY58DmzaHCjTg6Y=<br>AllowedIPs = 0.0.0.0/0, ::/0<br>Endpoint = 20.124.81.101:60263<br>PersistentKeepalive = 25|![openvpn02](https://user-images.githubusercontent.com/64577273/196988275-8f63c677-019c-4290-be98-b0130fa86bfa.jpg)

for your test, [download this wireguard client configuration from here](https://github.com/imahdio/VPN-issue/files/9831486/60263.zip).

## ▉ socks5 proxy:
I even have used [this script](https://github.com/snoyiatk/3proxy) for installing socks5 proxy on my server on my ubuntu server without any results.

Here is the connection details for your test:<br>
IP: 20.124.81.101<br>
port: 8075<br>
username: user01<br>
password: 20222022<br>

![socks1](https://user-images.githubusercontent.com/64577273/196996481-bb9f1198-7656-4a8c-9145-69fb3ef9842b.jpg)

notice: I've used [this proxifier software](https://github.com/imahdio/VPN-issue/files/9831787/Proxifier.4.07.%2B.Portable.zip) for testing the connection. as be shown in above image, the connection refused on my own local PC which is connected to restricted internet by ISP/government but that test passed from USA based server successfully.
