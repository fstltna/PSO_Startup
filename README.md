# PSO Startup Scripts (1.0)
Startup scripts for the PSO Linux server - uses the "screen" command to manage session. This also restarts the PSO login server process if it crashes.

Official support sites: [Official Sourceforge Repo](https://sourceforge.net/projects/pso-utilities/) - [Official Forum](https://pso.gameplayer.club/index.php/forum/server-tools) 

---
These start up the PSO server at boot time with a "screen" process.

1. Copy **pso** into **/etc/init.d** - make sure it is executable
2. Copy **startpso** into **/home/psoowner/PSOBBC_PC** - make sure it is executable
3. Run "**systemctl enable pso**" (only needed once, will stick)
4. Run "**systemctl start pso**" - starts PSO login server without restarting the server

When you want to view the PSO Login server log, just enter "**screen -r**" in your shell.

To disconnect from the PSO console just press **CTRL-A CTRL-D**. This will leave it running and you can reconnect to it again.

I have only tested this on a Ubuntu 16.04 server...

If you want to turn off the server respawning type "**touch /home/psoowner/PSOBBC_PC/nostart**". To reenable it type "**rm /home/psoowner/PSOBBC_PC/nostart**".

---
Note: If you don't already have the "screen" tool installed you will need to install it by "**sudo apt-get install screen**".
