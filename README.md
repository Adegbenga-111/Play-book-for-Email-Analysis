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

 ## Step 3 Finding Basic Information About The Sender :
 The basic information about the sender can be found on the top of the mail when it opened with note++,as shown in the image below :
 
 ![Alt The Mail Opened With Note++ with information about the sender highlighted](https://github.com/Adegbenga-111/Play-book-for-Email-Analysis/blob/main/meme.png)
*image 4: The Mail Opened With Note++ with information about the sender highlighted*

Information about the sender such as the mail application used , ip address of the mail apllication which can used to traced the location of sender to as particular degree , as showm in the image below :
 ![Alt The location of the sender](https://github.com/Adegbenga-111/Play-book-for-Email-Analysis/blob/main/Email%20Analysis%20-%20LetsDefend%20-%20Google%20Chrome%205_2_2024%201_43_04%20PM.png)
*image 5: The location of the sender *

## Step 3 Looking in the mail attachment :
It is important to analyze the mail attachment for malware or malicious activities in order to determine if file as malicious content, this can also be done to downloaded files . 
In this case the SHA(Secure Hashing Algorithm) 256 of the attactment in the mail is:**9909753bfb0ac8ab165bab3555233d03b01a9274a92e57c022f87ccbe51ca415**

In order to determine if the file is malicious, use the hash value to run a quick search on website like **VirusTotal**. The result is shown below

 ![Alt The Result From VirusTotal](https://github.com/Adegbenga-111/Play-book-for-Email-Analysis/blob/main/VirusTotal%20-%20File%20-%209909753bfb0ac8ab165bab3555233d03b01a9274a92e57c022f87ccbe51ca415%20-%20Google%20Chrome%205_11_2024%2011_31_05%20PM.png)
*image 6: The Result From VirusTotal*

From result gotten from VirusTotal the file is malicious , out of 72, 60 security vendors and 3 sandboxes flagged this file as malicious.


### Conclusion
Phishing is a form of social engineering and scam where attackers deceive people into revealing sensitive information or installing malware such as ransomware, which can can be done through sending emails to their target that why email analysis is importmant and also the education of all the stuff in an organization about all these of attack techniques should be taken serious. 




