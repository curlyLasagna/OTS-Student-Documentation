# Fusion Offline Rooms

When you get a ticket on a room that is "offline" in Fusion, it means that the control processor isn't communicating with the university network.

> Visit the TU Fusion website to check if the room is back online before heading out. There will be cases where it resolves itself.
> Your device has to be connected to `tu-secure` to be able to access the FUsion website

## Check Wall Port

Make sure the network cable is plugged into the correct wall jack (like printers, Crestron processors only work with the single port that was configured for the correct VLAN).  There should be at least three network drops in the room near the instructor’s podium (PC, Cable Cubby, and Crestron).  The Crestron cable should be<span style="color:red"> red </span> and the wall port should be marked with a “C”.

## Restart Processor

Unplug and replug the power cable in

## Ping Processor

Use the `ping` command from your PC to test network connectivity using the device’s hostname.

- If you get a reply from the processor by pinging it, it means that the processor is on the network.
- If you are still unable to reach the processor with Crestron Toolbox it is likely an issue with the hardware or programming in the processor.
- If the system has a Cisco router you will not get a reply but you should see the reserved IP address when pinging the hostname.

!!! example 

    ```
    ping CRESTRON-LA4305
    ```

    If it sends ICMP packets successfully, then it's reachable but that doesn't mean the problem is fixed

## Verify VLAN 

Verify the port is on the correct VLAN by obtaining the IP address.  It should be on the 41 VLAN. (i.e. 10.15.`41`.90)

Open Powershell and enter:
`nslookup crestron-<collection_code>`

## Check Cisco Router IP 

- Bring an ethernet cable and a laptop with an ethernet port or with an ethernet dongle.
Some aging Cisco routers, such as the RV042, need Internet Explorer to run.

- Connect your laptop to an empty network port on the Cisco router
- Open a browser and visit the router's webpage `192.168.1.1`

- Within the website, navigate:

Log → System Statistic and view the IP under “WAN1”.

## Send "Locked out port" ticket to networking

Upon visiting the room, and the touch panel doesn't show a TU logo in the middle, chances are the network port is locked out since the system isn't able to reach out to the university's network to query the logo.

To further confirm this assumption, check for any existing routers in the room and if it doesn't show that it doesn't have internet connectivity, then the assumption is confirmed

### Create an incident form

- Service: Network (Ethernet)
- Requestor: Anyone, but you

**Provide the following information:**

- Hostname of the system
- MAC address of the system

You can find the above information in the COLLECTIONS table in the CCLT techinfo database.

You can also find the MAC address by looking for a sticker somewhere on the processor.