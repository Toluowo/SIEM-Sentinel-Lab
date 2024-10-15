<h1>Failed RDP attempts to Honeypot Geolocation information</h1>

<h2>Description</h2>
This lab is focused on capturing and showing the analysis of brute force attempts made to a honeypot.
The PowerShell script in this repository is responsible for outputting Windows event log information and additionally fetches the geographic information of the attackers through a third-party API.

The implementation of the honeypot used a Windows 10 Pro host. Failed login attempts from RDP connections captured in the Windows event viewer were fed to the third-party API tool to get more detailed information from the IP of the attacker using the PowerShell script that served as the log exporter found in this repo.

The geolocation information generated from the API tool was used to plot a map in Azure Sentinel and screenshots can be seen below.


<h2>Live attacks from Lithuania as can be seen on the Powershell script</h2>
<img width="980" alt="Screenshot 2024-10-15 at 16 30 32" src="https://github.com/user-attachments/assets/1f583a4b-2540-4aea-beba-75f38f1531c6">
<br></br>
<h2>Live attacks on world map from different locations of the world over 5 days</h2>
<img width="980" alt="Screenshot 2024-09-26 at 17 43 30" src="https://github.com/user-attachments/assets/40632393-9b41-4faa-bd88-0a95117a3393">
<br></br>
<img width="980" alt="Screenshot 2024-09-26 at 18 19 33" src="https://github.com/user-attachments/assets/5a53a57f-0e5e-46f7-a075-50ade34e77cc">
<br></br>
<img width="980" alt="Screenshot 2024-09-29 at 15 20 35" src="https://github.com/user-attachments/assets/347b7903-658c-4da3-9497-f0de59e4974a">
<br></br>
<img width="980" alt="Screenshot 2024-09-30 at 10 34 44" src="https://github.com/user-attachments/assets/a6041059-8ba6-4240-9228-56969f61588d">
<br></br>
<img width="980" alt="Screenshot 2024-10-02 at 18 47 20" src="https://github.com/user-attachments/assets/f598fd39-569e-4715-babc-b2e9e9ca2539">
<br></br>
<img width="980" alt="Screenshot 2024-10-07 at 15 47 54" src="https://github.com/user-attachments/assets/1e1a7c72-4c8e-46d9-aec1-5c337fd9a222">

