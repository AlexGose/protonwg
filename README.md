# ProtonWG

The official [ProtonVPN](https://protonvpn.com/) Linux command line interface ([Linux CLI](https://protonvpn.com/support/linux-vpn-tool/)) does not support the [Wireguard](https://www.wireguard.com/) protocol yet.  Support for Wireguard is [expected soon](https://github.com/ProtonVPN/linux-cli/issues/64#issuecomment-1058224569). In the meantime ProtonWG is an unofficial Bash script for using ProtonVPN with Wireguard on Ubuntu 20.04 Linux.

ProtonWG requires downloading Wireguard configuration files and depends on [NetworkManager](https://networkmanager.dev/).  See the [directions](https://protonvpn.com/support/wireguard-configurations/) for using configuration files on Ubuntu 20.04 for the details.  Many of the official Linux CLI features are not available with ProtonWG.

In addition to Wireguard, ProtonWG supports a kill switch using Uncomplicated Firewall ([UFW](https://launchpad.net/ufw)).  ProtonWG also supports LAN access, Docker networking (on the 127.17.0.0/16 subnet), and host access to the Docker network while connected to a ProtonVPN server.

# Installation

Download the [protonwg](protonwg) file from this repository, and make the script file executable:

```
chmod a+x protonwg
```

# Usage

View the usage information:

```
./protonwg -h
```

```console
Usage: protonwg OPTIONS
    OPTIONS
      -h                         Help.  Prints this help message
      -c                         Connect to the VPN server
      -C                         Disconnect from the VPN server
      -d                         Disable Docker
      -D                         Enable Docker
      -f                         Set UFW firewall rules
      -F                         Reset (disable) UFW firewall rules.  Will
                                 occur before any new rules are set
      -n <network interface>     VPN network interface for firewall rules and
                                 connecting to, or disconnecting from, the VPN
      -a <ip address>            VPN server IP address for firewall rules
      -l <lan subnet>            LAN subnet for firewall rules (default 
                                 192.168.1.0/24)
      -s                         Show connection, docker, and UFW status
      -r                         Reboot computer when done
```

# Author

Alexander H Gose

# License

MIT License.  See the [LICENSE](LICENSE) file.

# Acknowledgements

A big thanks to Martin at ProtonVPN support, from whom I learned the UFW commands for the kill switch and commands for querying NetworkManager using the command line interface ([nmcli](https://networkmanager.dev/docs/api/latest/nmcli.html)).  Thank you to all the contributors of the projects mentioned in this [README](README.md) file.
