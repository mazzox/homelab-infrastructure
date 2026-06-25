Rocky Linux:

	> sudo nmtui
	> "Edit a connection"
	> IPv4 Configuartion: Manual
	> Address: (rocky-admin) 192.168.56.10/24 | (rocky-server01) 192.168.56.11/24

Ubuntu Server:

	> sudo nano /etc/netplan/00-installer-config.yaml
	> dhcp4: false
	> addresses: - 192.168.56.12/24
	> sudo netplan apply
