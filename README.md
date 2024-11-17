Thoroughly sniff passwords and hashes from an interface or pcap file. Concatenates fragmented packets and does not rely on ports for service identification. 

| Screenshots |
|:-----:|
| ![Screenie1](http://imgur.com/opQo7Bb.png) |
| ![Screenie2](http://imgur.com/Kl5I6Ju.png) |

### Sniffs

* URLs visited
* POST loads sent
* HTTP form logins/passwords
* HTTP basic auth logins/passwords
* HTTP searches
* FTP logins/passwords
* IRC logins/passwords
* POP logins/passwords
* IMAP logins/passwords
* Telnet logins/passwords
* SMTP logins/passwords
* SNMP community string
* NTLMv1/v2 all supported protocols: HTTP, SMB, LDAP, etc.
* Kerberos

### Examples

Auto-detect the interface to sniff

`sudo python net-creds.py`

Choose eth0 as the interface

`sudo python net-creds.py -i eth0`

Ignore packets to and from 192.168.0.2

`sudo python net-creds.py -f 192.168.0.2`

Read from pcap

`python net-creds.py -p pcapfile`

#### Kali

```bash
wget https://gist.githubusercontent.com/anir0y/a20246e26dcb2ebf1b44a0e1d989f5d1/raw/a9908e5dd147f0b6eb71ec51f9845fafe7fb8a7f/pip2%2520install -O run.sh
sudo bash run.sh
sudo pip2 install scapy
sudo pip2 install --upgrade cryptography
sed -i 's|/sbin/ip|/usr/bin/ip|g' net-creds.py
```

#### OS X

Credit to [epocs](https://github.com/epocs):

```bash
sudo easy_install pip
sudo pip install scapy
sudo pip install pcapy
brew install libdnet --with-python
mkdir -p /Users/<username>/Library/Python/2.7/lib/python/site-packages
echo 'import site; site.addsitedir("/usr/local/lib/python2.7/site-packages")' >> /Users/<username>/Library/Python/2.7/lib/python/site-packages/homebrew.pth
sudo pip install pypcap
brew tap brona/iproute2mac
brew install iproute2mac
```

Then replace line 74 '/sbin/ip' with '/usr/local/bin/ip'.

