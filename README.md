# Play-book-for-Email-Analysis
## Objective
Develop a phishing analysis playbook to standardize procedures for detecting, analyzing, and responding to phishing attacks. Enhance cybersecurity with clear guidelines for identifying, assessing risk, and mitigating threats. Empower teams to handle incidents and prevent unauthorized access and Minimize phishing impact and strengthen the organization's resilience against cyber threats.
### Skills Learned
- Understanding how to analyze email headers, content, and attachments for indicators of phishing.
- Learning how to recognize common phishing techniques and identifying suspicious emails.
- Learning to document phishing incidents, responses, and lessons learned to improve future incident handling and prevention strategies.
### Tools Used
- Letsdefend Email phishing  challenge
- Google (for research) .
## Steps
## Step 1 Network Design :
This network design framework offers a systematic approach to architecting, addressing, routing, and securing the organization's network, guaranteeing a resilient and adaptable infrastructure that can be expanded to meet future growth.
The network design diagram helps to give a clear idea of what the network infrastructure should look, and which the network device is connected to which device. since this project was a simulation, only few network devices were used , as shown in the image below

![Alt Network Diagram ](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/to%20be%20used%20as%20the%20network%20diagram.png)
*image 1: Network Diagram*
## Step 2 Router Configuration :
According to image 1 , there are three routers which are 192.168.1.1, ISP, 10.0.1.1. In order to create this network each of the router as to be configured using the cisco CLI(command line interface).
Router 192.168.1.1 Configuration:
 - Router>enable
 - Router#config t

**This lines of command is to move from User Exec mode to Global Configuration mode(All configuration are done in this mode) .**

-  Router(config)#int fa0/0
-  Router(config-if)#ip add 192.168.1.1 255.255.255.0 
-  Router(config-if)#no shut

 **This lines of command is to configure fast/ethernet0/0 for 192.168.1.1, as shown in the image below.**
 ![Alt fast/ethernet0/0 for 192.168.1.1 ](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/192.168.1.%204_27_2024%203_52_59%20PM.png)
*image 2: fast/ethernet0/0 for 192.168.1.1 *
-   Router(config-if)#exit
-   Router(config)#int fa0/1
-   Router(config-if)#ip address 13.2.5.3 255.0.0.0
-   Router(config-if)#no shut

  **This lines of command is to configure fast/ethernet0/1 for 192.168.1.1 , as shown in the image below.**
   ![Alt fast/ethernet0/1 for 192.168.1.1 ](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/192.168.1.%204_27_2024%203_52_53%20PM.png)
*image 3: fast/ethernet0/1 for 192.168.1.1 *
Router ISP Configuration:
-Router>enable
-Router#config t

**This lines of command is to move from User Exec mode to Global Configuration mode(All configuration are done in this mode) .**

- Router(config)#int fa0/0
- Router (config-if)#ip add 12.2.5.3 255.0.0.0
- Router(config-if)#no shut
- Router(config-if)#exit

 **This lines of command is to configure fast/ethernet0/0 for ISP , as shown in the image below.**
![Alt configure fast/ethernet0/0 for ISP](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/ISP%20(13.2.5.7)%20(12.2.5.3)%204_27_2024%203_53_22%20PM.png)
*image 4: fast/ethernet0/0 for ISP*
- Router(config)#int fa0/1
- Router(config-if)#ip add 13.2.5.7 255.0.0.0
- Router(config-if)#no shut

 **This lines of command is to configure fast/ethernet0/1 for ISP , as shown in the image below.**
 ![Alt  configure fast/ethernet0/1 for ISP ](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/ISP%20(13.2.5.7)%20(12.2.5.3)%204_27_2024%203_53_29%20PM.png)
*image 5: fast/ethernet0/1 for ISP*

Router 10.0.1.1 Configuration:
- Router>enable
- Router#config t

**This lines of command is to move from User Exec mode to Global Configuration mode(All configuration are done in this mode) .**

- Router(config)#int fa0/0
- Router(config-if)#ip add 12.2.5.4 255.0.0.0
- Router config-if)#no shut

**This lines of command is to configure fast/ethernet0/0 for 10.0.1.1 , as shown in the image below.**
![Alt configure fast/ethernet0/0 for ISP](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/10.0.1.1%204_27_2024%203_53_58%20PM.png)
*image 6: fast/ethernet0/0 for 10.0.1.1*

- Router(config-if)#exit
- Router(config)#int fa0/1
- Router(config-if)#ip add 10.0.1.1 255.255.255.0
- Router(config-if)#no shut

  
**This lines of command is to configure fast/ethernet0/1 for 10.0.1.1 , as shown in the image below.**
![Alt configure fast/ethernet0/0 for ISP](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/10.0.1.1%204_27_2024%203_54_09%20PM.png)
*image 7: fast/ethernet0/0 for 10.0.1.1*

**DEFAULT ROUTING CONFIGURATION ON ROUTER 192.168.1.1:.**
- Router>enable
- Router#config t
- Enter configuration commands, one per line. End with CNTL/Z.
- Router(config)#ip route 0.0.0.0 0.0.0.0 13.2.5.7
- Router(config)#

**DEFAULT ROUTING CONFIGURATION ON ROUTER 10.0.1.1:.**
- Router>enable
- Router#config t
- Enter configuration commands, one per line. End with CNTL/Z.
- Router(config)#ip route 0.0.0.0 0.0.0.0 12.2.5.3
- Router(config)#

## Step 3 VPN Configuration :
NOW CREATE VPN TUNNEL between  192.168.1.1 and 10.0.1.1:

 Fisrt Create A VPN Tunnel On ROUTER 192.168.1.1:
- Router#config t
- Router(config)#interface tunnel 10
- Router(config-if)#ip address 172.16.1.1 255.255.0.0
- Router(config-if)#tunnel source fa0/1
- Router(config-if)#tunnel destination 12.2.5.4
- Routerconfig-if)#no shut

NOW CREATE A VPN TUNNEL ON ROUTER 10.0.1.1:
- Router#config t
- Router(config)#interface tunnel 100
- Router(config-if)#ip address 172.16.1.2 255.255.0.0
- Router(config-if)#tunnel source fa0/0
- Router(config-if)#tunnel destination 13.2.5.3
- Router(config-if)#no shut

Now Do routing for created VPN Tunnel on Both Router 192.168.1.1 and 10.0.1.1:

 For Router 192.168.1.1:
  - Router(config)#ip route 192.168.2.0 255.255.255.0 172.16.1.2
 
  For Router 10.0.1.1:
  - Router(config)#ip route 192.168.1.0 255.255.255.0 172.16.1.1
 
## Step 3 END POINT DEVICES Configuration :
For the configuration of end point devices , just double click on the devcie and a plane will show up and move to config, then configuration was done as shown in the images shown below
![Alt Configuration for pc on 192.168.1.10  ](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/192.168.1.10%204_27_2024%203_51_06%20PM.png)
*image 8:Configuration for pc on 192.168.1.10 *

![Alt Configuration for laptop on 192.168.1.5  ](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/192.168.1.5%204_27_2024%203_51_32%20PM.png)
*image 9:Configuration for laptop on 192.168.1.5 *

![Alt Configuration for printer on 192.168.1.7 ](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/192.168.1.7%204_27_2024%203_52_07%20PM.png)
*image 10:Configuration for printer on 192.168.1.7 *

That for 192.168.1.0/255 network , next is the 10.0.1.0/255 which are configured the same way .

## Step 3 Testing of the network :

This is done to ensure that the network and end point devices are all communicating, the is done by using the command "ping" the ip address of the end point device. As shown below 

![Alt ping from 10.0.1.10 (pc) on the 10.0.1.0/255 network to 192.168.1.10 (pc) on the 192.168.1.0/255 network](https://github.com/Adegbenga-111/Building-An-Organization-VPN-Network-/blob/main/projecy/10.0.1.10%204_27_2024%203_59_28%20PM.png)
*image 10:ping from 10.0.1.10 (pc) on the 10.0.1.0/255 network to 192.168.1.10 (pc) on the 192.168.1.0/255 network*


### Conclusion
The process of designing and configuring a virtual VPN network for an organization on Packet Tracer requires careful planning and execution across various aspects of network architecture, addressing, routing, and security. By following a structured approach, including requirement analysis, network design, router configuration, and thorough testing, one can ensure the creation of a robust and scalable infrastructure that meets the organization's current needs while allowing for future growth and adaptability. This endeavor not only enhances technical skills in networking but also emphasizes the importance of security, reliability, and documentation in maintaining a resilient network environment.





