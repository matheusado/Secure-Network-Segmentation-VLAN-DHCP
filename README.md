<h1>Configuring-Secure-Network-Segmentation-VLAN-DHCP</h1>


<h2>Description</h2>
This project implements a secure, segmented network infrastructure using Cisco Packet Tracer. It includes a 14-node network with dynamic IP allocation via a DHCP server and a 6-node VLAN-isolated network hosting two dedicated web servers. The setup ensures secure communication, efficient IP management, and restricted inter-VLAN access, simulating a real-world environment for secure web application development and deployment.
<br />


<h2>Languages and Utilities Used</h2>

- Cisco Packet Tracer – Network simulation tool used to design and configure the entire network infrastructure.
- DHCP (Dynamic Host Configuration Protocol) – For automatic IP address allocation to the 14-node network.
- VLAN (Virtual LAN) – Used to isolate web servers in the 6-node network.
- Switch Configuration (CLI) – Command Line Interface used to set up VLANs and port assignments.
- Router Configuration (CLI) – For inter-network routing and communication rules.
- Basic Networking Protocols – Including TCP/IP, ICMP, and ARP for connectivity testing.


<h2>Environments Used </h2>

- macOS Ventura 13.7.4(21H2)
- Cisco Packet Tracer
- Switch CLI Environment
- Router CLI Environment
- End Device Simulation

<h2>Program walk-through:</h2>

<p align="center">
Set up a 14-node network. Start by launching Cisco Packet Tracer: <br/>
<img src="https://i.imgur.com/ZRUAO4Y.png"/>
<br />
<br />
Click on Switches, select 2960-24TT and drag it to the main screen:  <br/>
<img src="https://i.imgur.com/DKVHU3t.png"/>
<br />
<br />
Click on End Devices, select PC-PT and drag 12 computers to the main screen: <br/>
<img src="https://i.imgur.com/ZVtIWQA.png"/>
<br />
<br />
Click on Connections and select Copper Straight-Through, click on Switch0, choose FastEthernet0/1 port:  <br/>
<img src="https://i.imgur.com/ckiG9oH.png"/>
<br />
<br />
Click on PC0 and select FastEthernet0 to establish the connection between PC0 and Switch0:  <br/>
<img src="https://i.imgur.com/J4XW21T.png"/>
<br />
<br />
Click on Switch0 again, select FastEthernet0/2 port, then click on PC1 and select FastEthernet0 port:  <br/>
<img src="https://i.imgur.com/6dD4LbQ.png"/>
<img src="https://i.imgur.com/LWjVI9E.png"/>
<br />
<br />
Repeat these steps to connect the remaining 10 PCs:  <br/>
<img src="https://i.imgur.com/jx3tmH0.png"/>
<br />
<br />
Set up a 6-node network, start by clicking on Switches then select 2960-24TT and drag it to the main screen:  <br/>
<img src="https://i.imgur.com/YORcN45.png"/>
<br />
<br />
Click on End Devices, select PC-PT then drag 5 PCs to the main screen: <br/>
<img src="https://i.imgur.com/KZW3PCy.png"/> 
<br />
<br />
Click on Connections, select Copper Straight-Through cable, then click on Switch1 then choose FastEthernet0/1 port:    <br/>
<img src="https://i.imgur.com/u5kG4hG.png"/>
<br />
<br />
Click on PC12 and choose FastEthernet0 port to establish connection:  <br/>
<img src="https://i.imgur.com/11nBbDs.png"/>
<br />
<br />
Repeat the steps to connect the remaining 4 PCs, remember to choose different ports on the Switch:  <br/>
<img src="https://i.imgur.com/3ALhhdS.png"/>
<br />
<br />
Now connect the 14-node and 6-node networks. Start by clicking on Routers, select 2621XM Router and drag it to the main screen:  <br/>
<img src="https://i.imgur.com/mi7IexH.png"/>
<br />
<br />
Click on Connections, select Copper Straight-Through cable then click on 2621XM Router0 and select FastEthernet0/0 port:  <br/>
<img src="https://i.imgur.com/UPF9oYw.png"/>
<br />
<br />
Click on Switch0 and select FastEthernet0/13 port:  <br/>
<img src="https://i.imgur.com/aHX16lm.png"/>
<br />
<br />
Click again on 2621XM Router0 and select FastEthernet0/1 port: <br/>
<img src="https://i.imgur.com/OobOu50.png"/>
<br />
<br />
Click on Switch1 and select FastEthernet0/6 port:<br/>
<img src="https://i.imgur.com/fA2MX65.png"/>
<br />
<br />
Now, configure VLAN for web server isolation. Start by clicking on End Devices, select Server-PT and drag it to the main screen:  <br/>
<img src="https://i.imgur.com/WGkJSHp.png"/>
<br />
<br />
Click on Connections, select Copper Straight-Through cable then click on Server0 and select FastEthernet0 port: <br/>
<img src="https://i.imgur.com/44i9p1G.png"/>
<br />
<br />
Click on Switch0 and select FastEthernet0/14 port to establish connection: <br/>
<img src="https://i.imgur.com/4SvuZt8.png"/>
<br />
<br />
In the browser, paste the link given below and press enter:
  
https://www.calculator.net/ip-subnet-calculator.html <br/>
<img src="https://i.imgur.com/bGY1EjM.png"/>
<br />
<br />
Select 255.255.255.240/28 as Subnet and 192.168.110.0 as IP Address, click on calculate, then review the Usable Host IP Range, Number of Usable Hosts, and Subnet Mask from the output: <br/>
<img src="https://i.imgur.com/DlOwJK7.png"/>
<br />
<br />
Navigate back to Packet Tracer and click on Server0, select Desktop then IP Configuration: <br/>
<img src="https://i.imgur.com/VBj4BC9.png"/>
<br />
<br />
Select Static and enter 192.168.110.1 as the IP Address, Enter 255.255.255.240 as Subnet Mask and 192.168.110.14 as Default Gateway: <br/>
<img src="https://i.imgur.com/UjAolmc.png"/>
<br />
<br />
Click on Services tab, select DHCP, turn on the DHCP service, enter Pool001 as Pool Name, enter 192.168.110.14 as Default Gateway, 192.168.110.2 as Start IP Address, 255.255.255.240 as Subnet Mask, 14 as Maximum number of Users and click in Add: <br/>
<img src="https://i.imgur.com/fU5OiD0.png"/>
<br />
<br />
Click on Router0, select Config, click on FastEthernet0/0, enter 192.168.110.14 as IP Address, enter 255.255.255.240 as Subnet Mask and enable Port Status: <br/>
<img src="https://i.imgur.com/IvWx7yX.png"/>
<br />
<br />
The next steps will serve to enable DHCP and configure a DHCP pool. Click on Router0, select CLI tab and type the following commands (1 per line):

Router>enable
Router#configure terminal
Router(config)#ip dhcp excluded-address 192.168.110.14
Router(config)#ip dhcp pool LAN
Router(dhcp-config)#network 192.168.110.0 255.255.255.240
Router(dhcp-config)#default-router 192.168.110.14
Router(dhcp-config)#dns-server 8.8.8.8
Router(dhcp-config)#exit


P.S.: 192.168.110.14 is excluded because the router itself is using it. 
<br/>
<img src="https://i.imgur.com/oZqLJtz.png"/>
<br />
<br />
Navigate back to the main screen and click on PC0, select Desktop and click on IP Configuration: <br/>
<img src="https://i.imgur.com/YqVhXSk.png"/>
<br />
<br />
Select DHCP, confirm the successful request message, then repeat these steps for the remaining 11 PCs: <br/>
<img src="https://i.imgur.com/BmqbuhR.png"/>
<br />
<br />
Configuring DHCP and IP addresses in the 6-node network. In the browser, paste the link given below and press enter:

https://www.calculator.net/ip-subnet-calculator.html <br/>
<img src="https://i.imgur.com/K1jM43k.png"/>
<br />
<br />
Select 255.255.255.248/29 as Subnet, enter 192.168.120.0 as IP Address and click in calculate: <br/>
<img src="https://i.imgur.com/L7as3AT.png"/>
<br />
<br />
Review the Usable Host IP range, Number of Usable Hosts, and Subnet mask from the output: <br/>
<img src="https://i.imgur.com/wSyu9VW.png"/>
<br />
<br />
Navigate back to Packet Tracer, click on PC12, select Desktop and click on IP Configuration: <br/>
<img src="https://i.imgur.com/pmIvPyB.png"/>
<br />
<br />
Select Static and enter 192.168.120.1 as the IP Address, enter 255.255.255.248 as Subnet Mask and 192.168.120.6 as Default Gateway. Repeat these steps on the next 4 PCs, use 192.168.120.2 as the IP Address for PC13, 192.168.120.3 as the IP Address for PC14, 192.168.120.4 as the IP Address for PC15 and 192.168.120.5 as the IP Address for PC16, Subnet Mask and Default Gateway remains the same as PC12: <br/>
<img src="https://i.imgur.com/C8C6Pqf.png"/>
<img src="https://i.imgur.com/eKuSkTI.png"/>
<br />
<br />
Now click on the Router0, go on Config tab and select FastEthernet0/1, enter 192.168.120.6 as IP Address, 255.255.255.248 as Subnet Mask and Enable Port Status: <br/>
<img src="https://i.imgur.com/3nRzJWc.png"/>
<br />
<br />
Click on Switch1, select Config tab then VLAN Database. Enter 10 as VLAN number, WebServerVlan as VLAN name then click in Add: <br/>
<img src="https://i.imgur.com/5uHBZED.png"/>
<br />
<br />
Select PC12 and PC13 to use as servers. Click on PC12, go on Config tab then enter Server1 as 
Display name. Repeat the same steps on PC13 but name it as Server2: <br/>
<img src="https://i.imgur.com/2t65gp6.png"/>
<br />
<br />
Click on PC14 then name it as Admin: <br/>
<img src="https://i.imgur.com/J9ad7Wn.png"/>
<br />
<br />
Click on Switch1, click on Config, then FastEthernet0/1 tab. At the VLAN field, click in the arrow then select 10:WebServerVlan: <br/>
<img src="https://i.imgur.com/Rbh6xgi.png"/>
<br />
<br />
Repeat the same steps on FastEthernet0/2 and FastEthernet0/3 tabs:

P.S.: Now we have 1 Administrator computer which will manage the 2 PCs Servers on the same VLAN. <br/>
<img src="https://i.imgur.com/3PMj5Ne.png"/>
<img src="https://i.imgur.com/IMCakpQ.png"/>
<br />
<br />
Click on PC1, select Desktop and click on Command Prompt: <br/>
<img src="https://i.imgur.com/pxJAfae.png"/>
<br />
<br />
Run the following command:

ping 192.168.110.2 <br/>
<img src="https://i.imgur.com/j3i1437.png"/>
<br />
<br />
Run the following command to see the route: 
tracert 192.168.120.4 <br/>
<img src="https://i.imgur.com/cb9NBoP.png"/>
<br />
<br />
Click on PC15, select Desktop then Command Prompt. Then run the following command to test and validate:

ping 192.168.120.5 <br/>
<img src="https://i.imgur.com/Agjmgv8.png"/>
Note: Both are in the same VLAN, allowing them to ping each other. 
<br />
<br />
Now run the following command: 

ping 192.168.120.2 <br/>
<img src="https://i.imgur.com/NSfL3LN.png"/>
Note: They are in different VLANs, so they will not be able to ping each other. 
<br />
<br />
Conclusion

This project successfully demonstrated the implementation of a secure and segmented network infrastructure using Cisco Packet Tracer. A 14-node network was configured with DHCP-enabled dynamic IP addressing to streamline IP management and reduce administrative overhead. Additionally, a 6-node network was established, incorporating VLAN configuration to isolate two dedicated web servers, ensuring secure and controlled communication for web application development.
Through the integration of DHCP, VLANs, and inter-network connectivity, the project met all requirements for efficient IP address allocation, network segmentation, and communication control. The resulting infrastructure supports secure development environments while maintaining scalability and administrative efficiency. This hands-on experience reinforced essential networking concepts and practical skills in secure network design and configuration.


</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
