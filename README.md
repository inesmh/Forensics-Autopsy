<h1>Computer Forensics - Autopsy</h1>

<h3>Objective</h3>
The aim of this project is to analyze an image from a device and answer the following questions.
<br /> <br />
<h3>Skills Learned</h3>
● Reverse Engineering <br />

<br />
<h3>Tools Used</h3>
● Autopsy <br />
<br />

<h3>Steps</h3>
QUESTION 1 
<br />
Which device was this image taken from?
<br />
We look up the Live Data folder to see the information related to the device. There, we opened the file device_properties.txt
<br />
In this file we can see that the device is a LGE Nexus 5X.
<br />
<img width="542" alt="autopsy1" src="https://github.com/user-attachments/assets/ed047c44-c84c-4ca4-ae6e-367a37c97dcf">
<br />
*Ref 1: Autopsy device info*
<br />
<br />
QUESTION 2 
<br />
What is the device’s IMEI number?
<br />
First we saw an IMEI number in the screenshot located here:+
<br />
"/LogicalFileSet1/MBimage/Mobile_image/ adb-data/shared/0/Pictures/Screenshots/Screenshot_20191024-113820.png"
<br />
<img width="494" alt="autopsy2" src="https://github.com/user-attachments/assets/61429ade-72fb-4c47-8e91-2e6e921692c6">
<br />
*Ref 2.1: Autopsy screenshots*
<br />
<br />
In this image it appears the IMEI number 353626075095047. To confirm that it was of the given device, we searched this number in Autopsy keyword search, finding it on the database agent_sim.db.
<br />
<img width="512" alt="autopsy3" src="https://github.com/user-attachments/assets/294e3692-0285-4927-ab28-54a2fea88dd4">
<br />
*Ref 2.2: Autopsy database agent_sim.db*
<br />
<br />
The device's IMEI number 353626075095047 is then correct.
<br />
<br />
QUESTION 3
<br />
What mobile network does the SIM belong to?
<br />
The network the SIM belongs to can be seen actually while resolving the previous questionin the agent_sim.db.
<br />
As it can be seen in the following image, the SIM operator is Safaricom.
<br />
<img width="515" alt="autopsy4" src="https://github.com/user-attachments/assets/23c6fda3-fa53-4a12-9e71-5e37b4f2f1a5">
<br />
*Ref 3: Autopsy database agent_sim.db*
<br />
<br />
QUESTION 4
<br />
When was this text message received “Nitumie kwa hii namba plz (0707701525) itatoa jina Douglas Mugendi.”
<br />
We looked up in the keyword search the message received (Nitumie kwa hii namba plz) and we were redirected to the agent_mmssms.db.
<br />
Once in the database we looked for the message again filtering the results with the specific body of the message.
<br />
The message was received on 2019/10/23 14:32:49.
<br />
<img width="432" alt="autopsy5" src="https://github.com/user-attachments/assets/a5e820ed-6ef1-4cf4-9d32-06df3c77f86e">
<br />
*Ref 4: Autopsy database agent_mmssms.db*
<br />
<br />
QUESTION 5
<br />
What was the number that send the message “Nitumie kwa hii namba plz (0707701525) itatoa jina Douglas Mugendi.”?
<br />
Again, while solving the previous question we got the answer for this one. In the same database agent_mmssms.db, once located the message with the given body, we get who sent the message.
<br />
Once in the database we looked for the message again filtering the results with the specific body of the message.
<br />
The message was sent by number +254794660124.
<br />
<img width="434" alt="autopsy6" src="https://github.com/user-attachments/assets/9a498d64-6b91-440d-b85d-af9417e5d42a">
<br />
*Ref 5: Autopsy database agent_mmssms.db*
<br />
<br />
QUESTION 6
<br />
An international call was received by the device. Which country did the call come from?
<br />
We looked up databases related to received calls, and inside Agent data, in the database contacts2.db we observed several calls, and one with the prefix +44 (which corresponds to UK).
<br />
<img width="263" alt="autopsy7" src="https://github.com/user-attachments/assets/fef0c08f-b331-4bb9-a20f-1699a8f6c9f8">
<br />
*Ref 6: Autopsy database contacts2.db*
<br />
<br />
QUESTION 7
<br />
What is the name of the 7-letter wireless network the device has connected to at some point?
<br />
We looked for databases related to wifi and we obtained the wifi.db. There we can see the 7-letter network called kongoni.
<br />
<img width="227" alt="autopsy8" src="https://github.com/user-attachments/assets/fcc6ab08-30b3-4880-b8e6-1f75505270fc">
<br />
*Ref 7: Autopsy database Agent Data/wifi.db*
<br />
<br />
QUESTION 8
<br />
What is the mobile device owner’s username on Twitter?
<br />
We looked for “account” in the keyword search.
<br />
<img width="298" alt="autopsy9" src="https://github.com/user-attachments/assets/f1844578-e481-4e67-9c48-97cf81e25582">
<br />
*Ref 8.1: Autopsy keyword search*
<br />
<br />
We obtained the result of several accounts, such as twitter, facebook, telegram and others.
<br />
The device owner’s username on Twitter is KamiLenana.
<br />
<img width="482" alt="autopsy10" src="https://github.com/user-attachments/assets/ab08dcf5-1edf-4675-87e7-a6532bef0d0d">
<br />
*Ref 8.2: Autopsy file account.txt*
<br />
<br />
QUESTION 9
<br />
List the google accounts that were linked to this device?
<br />
As can be seen in the image from the question above, The google accounts that were linked to this device are cocoash100@gmail.com and lenanakami@gmail.com.
<br />
<br />
QUESTION 10
<br />
Identify the forensics app installed on the device?
<br />
First we opened the folder “apps” to have a look on the apps that are installed on the device, to see if there is something related to forensics.
<br />
We saw the app called com.viaforensics.android.aflogical_ose, which as its name indicates, it is used for forensics.
<br />
<img width="412" alt="autopsy11" src="https://github.com/user-attachments/assets/29270129-a516-4983-ab1d-1c50d0ad98c7">
<br />
*Ref 10.1: Autopsy apps folder*
<br />
<br />
In this folder, we can find the apk.
<br />
<img width="500" alt="autopsy12" src="https://github.com/user-attachments/assets/b8a4eb83-e7cf-40ce-97c2-4568edf70c40">
<br />
*Ref 10.2: Autopsy apk of forensics app*
<br />
<br />
