# Get-Enumeration
A 1-Line data collection and exfiltration method utilising PowerShell and HTTP Headers

This one-line PowerShell script is well suited to USB RubberDucky/Flipper Zero/BadUSB attacks where speed is of the essence. The script would suit someone working under the following assumptions/conditions:

- Target machine is not running as an administrative user.
- Sending external emails or file uploads are prohibited (due to firewall/EDR rules etc.)
- Attacker is able to spawn a PowerShell prompt.

This script works by collecting various pieces of information about the operating environment using built-in PowerShell commands. The output of these commands is then Base64 encoded before being sent via a HTTP GET request to a server of your choice. To assist in obfuscation, the data is sent using HTTP Headers as these are less likely to be viewed by a human if there is any suspicion of data exfiltration.

**Remember to update the URL in the script!**

The script currently pulls the following information:

- Hostname
- Local IP Address info for DHCP enabled interfaces
- Wifi SSIDs and security Keys
- Computer Info: 
    - Organization
    - RegisteredOwner
    - DNSHostName
    - Domain
    - Current UserName
    - Device Manufacturer
    - Device Model
    - Device Name
    - OS Version
    - BIOS Version
    - BIOS Serial Number
- Windows Patch Level
- Running Services (currently broken!)
- Local Users

These are all added to their own X-Headers in base64 format and sent via a HTTP GET request to your chosen URL
