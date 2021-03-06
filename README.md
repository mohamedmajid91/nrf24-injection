A tool set for sniffing devices and launching attacks with Crazyradio.
Based on [BastilleResearch](https://github.com/BastilleResearch/nrf-research-firmware.git "nrf-research-firmware")'s research.

### Setting Up
Install additional modules
```sh
sudo apt-get install sdcc binutils python python-pip
sudo pip install -U pip
sudo pip install -U -I pyusb
sudo pip install -U platformio
```

### Supported Devices
| Device  | Sniff | Attack | Details |
| ----------------- | ----------------- | ----------------- | ----------------- |
| AmazonBasics | Yes(unresponsive) | Yes | Mice control and HID Injection |
| Logitech Mice | Yes | Yes | Mice control |


### How to Use
```sh
# Run directly
sudo python app.py
# For Crazyradio PA users
sudo python app.py -l
# Check for help documents
sudo python app.py -h
```

### How to Use Launch Attacks
```sh
# Please check attacking rules in 'devices/*.py' for details
# Further infomation will added to here once I have time
# Attacking thread sleeps for 100 milliseconds
<SLP(100)>
# Move mouse by 100*100 only
<MOV(100,100)>
# Press Left button only (Mouse)
<MOV(L)>
# Move mouse by 100*100 and press Left, Right and Middle buttons
<MOV(100,100,LMR)>
# Release the buttons for mice, you can send another MOV command without any buttons
<MOV(0,0)>
<MOV()>
# Send keystrokes to release all keys
<RLS>
# Send 'Windows + r' key combination
<WIN+r>
# Send 'Ctrl + Alt + Delete' key combination
<CTRL+ALT+DEL>
# For Windows computers, the following commmand will open the Powershell and then open the Caculator
<RLS><WIN+r><RLS><SLP(500)><RLS>powershell<ENTER><RLS><SLP(500)><RLS>calc<ENTER><RLS>
```

License
----
GPL
