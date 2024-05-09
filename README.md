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
## Step 1 Opening of Zip files :
Opening the zip file containing the email ,but in this case we have two zip files 
![Alt The Files Used In this Analysis](https://github.com/Adegbenga-111/Play-book-for-Email-Analysis/blob/main/Email%20Analysis%20-%20LetsDefend%20-%20Google%20Chrome%205_2_2024%201_08_17%20PM.png)
*image 1:The Files Used In this Analysis *

Opening the zip files with the password:**infected**

![Alt Openind The Files Used In this Analysis](https://github.com/Adegbenga-111/Play-book-for-Email-Analysis/blob/main/Email%20Analysis%20-%20LetsDefend%20-%20Google%20Chrome%205_2_2024%201_12_11%20PM.png)
*image 2:Openind The Files Used In this Analysis *

## Step 2 Opening Mail with the necessary Application:
Opening the mail with the email application in this case it's thunderbird , to read the content of the mail frist since basic infromation about the sender can be found easly.

![Alt The Mail Opened With Thunderbird](https://github.com/Adegbenga-111/Play-book-for-Email-Analysis/blob/main/Email%20Analysis%20-%20LetsDefend%20-%20Google%20Chrome%205_2_2024%201_31_21%20PM.png)
*image 3: The Mail Opened With Thunderbird *

  The next application used is the note++ , this is a code editor which will give us the **HTMl** structure of the mail , this helps me to have a look at a molecular level.

  ![Alt The Mail Opened With Note++](https://github.com/Adegbenga-111/Play-book-for-Email-Analysis/blob/main/Email%20Analysis%20-%20LetsDefend%20-%20Google%20Chrome%205_2_2024%201_16_23%20PM.png)
*image 4: The Mail Opened With Note++*

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





