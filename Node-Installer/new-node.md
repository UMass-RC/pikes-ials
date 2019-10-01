How to Provision New Pikes Nodes:

1. In the file /cm/node-installer/scripts/node-installer.conf, set "setupBMC" to "true" (This should be false when not adding new nodes)
2. Provision using node wizard in Bright CM like normal, and if the BMC controller is configured successfully, great. If not:
	a. Rename /cm/node-installer/scripts/node-installer/configure_ipmi.pl to configure_ipmi.pl.old
	b. Rename /cm/node-installer/scripts/node-installer/configure_ipmi.pl.new to configure_ipmi.pl
	c. Run through node installer again, no reboot required. This should configure IPMI successfully.
	d. Once done installing new nodes, restore the original configure_ipmi file.
3. Once done, revert step #1 in the same file.