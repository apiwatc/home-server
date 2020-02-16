## **Configure WiFi Connections**
- Determine the name of the WiFi interface:

        # controlling NetworkManager and reporting network status
        $ nmcli d

        # used to display and change the parameters of the wifi network
        $ iwconfig wlan0

- Make sure the WiFi radio is on
        
        $ nmcli r wifi on

- List the available WiFi networks

        $ nmcli d wifi list

- Connect to the access point "name-of-wifi"

        $ nmcli d wifi connect "name-of-wifi" password <password>

