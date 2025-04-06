<ol>
<li>Create a Microsoft Azure account. New users are usually given a 1-month access and a $200 subscription credit.</li>
<li>Navigate to portal.azure.com and create a new virtual machine (VM), which will be our honeypot in this scenario. Create a resource group to group your resources in one place.</li>
<li>Configure inbound rules to allow inbound traffic as much as possible. This is to be able to gather the logs and the failed login attempts in the shortest time possible,</li>
<li>Create a log analytics workspace that will enable us to gather and organize the logs we will be compiling.</li>
<li>Connect the log analytics workspace to the VM created earlier in step 2.</li>
<li>Connect the Azure Sentinel (SIEM) to the workspace.</li>
<li>Wait for the workspace and the sentinel to be properly connected to the VM, and then open Microsoft Remote Desktop (Comes installed if you're using a Windows host, and is downloadable for Mac users from the store) to connect to the VM</li>
<li>In your VM, either turn off the firewall or update settings to allow ICMP requests, this is to allow as many connections as possible to the honeypot VM. Verify the settings with a ping request to the honeypot to be sure that all settings are updated and that the honeypot is ready to serve its purpose.</li>
<li>Download or copy the log exporter file "Failed_rdp_Log_Exporter.ps1" located in this repository to the honeypot VM. Then open the PowerShell ISE application and run it. This script gathers the location (longitude and latitude) information from the IP addresses of computers around the world with failed login attempts to the honeypot.</li>
<li>Update the $API_KEY at the top of the script with your API key, which can be generated from "https://ipgeolocation.io"</li>
<li>The free/basic API key will only work for a thousand API calls per 24 hours. Anything more than this will require a subscription. For this lab, a free plan was used.</li>
<li>Navigate back to the log workspace to create a custom log that will fetch the raw data with the geographic information from the Powershell script.</li>
<li>Copy the query from the "Sentinel_Query" file in the repository and run it in the Workbooks window (Monitoring > Workbooks).</li>
<li>Change the visualization option to "maps" to start seeing the failed RDP logins on the world map.</li>
<li>Configure other map settings as desired.</li>
</ol>
