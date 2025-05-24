#arch 
To open and connect proton VPN with out manual entry:

step 1: create a credentials.txt  witch should contains  the username and pass-key provided by the proton VPN to connect via CLI

step 2: create an bash script (.sh) that contains the following code
```#!/bin/bash

# Ensure the credential file is readable only by the user
chmod 600 ~/vpn_credentials.txt

# Run OpenVPN with auth-user-pass
sudo openvpn --config "/home/wildfox/Desktop/jp-free-2.protonvpn.udp.ovpn" --auth-user-pass ~/vpn_credentials.txt
```

Now to connect open terminal and run the script with 
```
./<file_name.sh>

```