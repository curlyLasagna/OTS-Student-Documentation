# Fusion Offline Rooms

When you get a ticket on a room that is "offline" in Fusion, it means that control processor isn't communicating with the university network.

> Visit [Fusion](crestron2.towson.edu/Fusion/WebClient/monitoring2/pages/default?sp=&rr=60#critical-status-tab) to check if the room is back online before heading out. There will be cases where it resolves itself.

## Check Wall Port

Make sure the network cable is plugged into the correct wall jack (like printers, Crestron processors only work with the single port that was configured for the correct VLAN).  There should be at least three network drops in the room near the instructor’s podium (PC, Cable Cubby, and Crestron).  The Crestron cable should be red and the wall port should be marked with a “C”.

## Restart Processor

Unplug and replug the power cable in

## Ping Processor

Use the Ping command from your PC to test network connectivity using the device’s hostname. If you get a reply from the processor by pinging it, it means that the processor is on the network.  If you are still unable to reach the processor with Crestron Toolbox it is likely an issue with the hardware or programming in the processor.  If the system has a Cisco router you will not get a reply but you should see the reserved IP address when pinging the hostname.

### Example

`ping CRESTRON-LA4305` 

## Verify VLAN 

Verify the port is on the correct VLAN by looking at the IP address.  It should be on the 41 VLAN. (i.e. 10.15.41.90)

Open Powershell and enter:
`nslookup crestron-<collection_code>`

## Check Cisco Router IP 

- Bring an ethernet cable and a laptop with an ethernet port or with an ethernet dongle.
Some aging Cisco routers, such as the RV042, needs to Internet Explorer to run.

- Connect your laptop to an empty network butport on the Cisco router and log into the router itself (192.168.1.1).
- Navigate:

> Log > System Statistic and view the IP under “WAN1”.

## Send "Locked out port" ticket to networking

Upon visiting the room, and the touch panel doesn't show a TU logo in the middle, chances are the network port is locked out since the system isn't able to reach out to the university's network to query the logo.

To further confirm this assumption, check for any existing routers in the room and if it doesn't show that it doesn't have internet connectivity, then the assumption is confirmed

Create an incident form
- Service: Network (Ethernet)
- Requestor: Anyone, but you

Provide the following information:
- Hostname of the system
- MAC address of the system

You can find the above information in the COLLECTIONS table in the CCLT techinfo database