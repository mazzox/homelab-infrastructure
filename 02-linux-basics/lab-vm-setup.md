Building a homelab with 3 different linux VMs

Why: For the simplicity of the lab and getting use to working with multiple Linux servers I've installed 2 Rocky linux and 1 ubuntu server.
Rocky linux is the closest distro to Redhat so i've chose it to be my main distro for getting more experience on how enterprises are doing the job.

What did i do: 
	# changed VMs hostname 
		> VM1 -> rocky-admin
		> VM2 -> rocky-server01
		> VM3 -> ubuntu-server01

	# installed important tools for the stack
		> bind-utils
		> net-tools
		> traceroute
		> wget / curl / git / vim

	# installed SSH
		# systemctl enable sshd
		# sudo systemctl start sshd
		# systemctl status sshd


