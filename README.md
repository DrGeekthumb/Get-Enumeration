# Get-Enumeration
A 1-Line data collection and exfiltration method utilising PowerShell and HTTP Headers

This one-line PowerShell script is well suited to USB RubberDucky/Flipper Zero/BadUSB attacks where speed is of the essence. The script would suit someone working under the following assumptions/conditions:

- Target machine is not running as an administrative user.
- Sending external emails or file uploads are prohibited (due to firewall/EDR rules etc.)
- Attacker is able to spawn a PowerShell prompt.

This script works by collecting various pieces of information about the operating environment using built-in PowerShell commands. The output of these commands is then Base64 encoded before being sent via a HTTP GET request to a server of your choice. To assist in obfuscation, the data is sent using HTTP Headers as these are less likely to be viewed by a human if there is any suspicion of data exfiltration.

**Remember to update the URL in the script!**



