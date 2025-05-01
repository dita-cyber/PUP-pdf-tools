# PUP-pdf-tools

I received an alert related to "Anomaly detected in ASEP registry"

Alert description:

An identified process registered a suspicious command or file in ASEP registry key, where it will be run after a reboot.An attacker may place a malicious piece of software in such a location to prevent losing access if a machine is turned off.

Threat Description: The Autorun or the ASEP (AutoStart Extension Point) Registry Keys control what is launched for the user when they initially log in. Attackers can modify specific keys and attain persistence on an exploited machine. In doing so, this can allow a binary to be executed with elevated privileges.

Microsoft Defender timeline showed that processSetupHost.exe changed registry value XXX\Software\Microsoft\Windows\CurrentVersion\Run followed by events related to PUP (potential unwanted program) PDF tools :

SetupHost.exe created file SmartConvertPDF_48160421.msi 
SHA1: f7e5e48f6444c7b8f42fe6e0aaa4e0bd17f291f4

SetupHost.exe created file smartviewpdf.msi
SHA1: e1c6f8ae524d8bd9ef91fbeccfcb8952b00d25fa

VirusTotal Analysis:
 
(images to be added)

(images to be added)

PUPs, or Potentially Unwanted Programs, are typically installed alongside other software and serve as marketing tools. They often modify browser settings or display intrusive advertisements, the most common form being adware. Although these binaries have a low reputation based on their malicious OSINT, they are classified as PUPs due to their unusual persistence mechanisms. PDF tools with similar behavior are commonly observed across various environments.

VirusTotal scans for both file hashes revealed their classification as PUPs. While not inherently malicious, these programs are undesirable due to their adware-like behavior and are recommended for removal.

Recommendation provided:

• Manual Uninstallation: Remove the unwanted programs directly from the affected hosts.
• Run Antivirus Scan: Conduct a thorough scan to identify and eliminate any remaining threats.
• Blacklist File Hashes: Implement hash blacklisting within your environment's EDR tools to prevent future occurrences.
• Remove Registry Key: Delete the modified registry key to eliminate persistence mechanisms.


