# Event IDs:
| Sysmon ID | Windows ID | Tag | Event | Frequency | Notes |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 4688 | ProcessCreate | Process Create | Noisy | Hash of process/file captured! |
| 2 | 4657 | FileCreateTime | File creation time | | Timestomping?! |
| 3 | 5156 | NetworkConnect | Network connection detected | Noisy | Provides some name resolution of IP |
| 4 | | N/A | Sysmon service state change (cannot be filtered) |
| 5 | 4689 | ProcessTerminate | Process terminated | Noisy |
| 6 | 6, 219, 7026 | DriverLoad | Driver Loaded | | Detect device drivers loading |
| 7 | | ImageLoad | Image loaded | Noisy | Most malware is NOT Signed... collect signed false only |
| 8 | | CreateRemoteThread | CreateRemoteThread detected | | Detect code injections used by malwareCredential, inject their code into the LSASS process |
| 9 | | RawAccessRead | RawAccessRead detected | | Detect dropping off SAM or NTDS.DIT from compromised hosts |
| 10 | | ProcessAccess | Process accessed | Noisy |
| 11 | 4663 | FileCreate | File created | Noisy |
| 12 | 4657 | RegistryEvent | Registry object added or deleted | Noisy | Can show brower downloads |
| 13 | 4657 | RegistryEvent | Registry value set | Noisy |
| 14 | 4657 | RegistryEvent | Registry object renamed |
| 15 | | FileCreateStreamHash | File stream created |
| 16 | | N/A | Sysmon configuration change (cannot be filtered) |
| 17 | | PipeEvent | Named pipe created |
| 18 | | PipeEvent | Named pipe connected |
| 19 | 5861, 5858, 5859 | WMI EventFilter activity |
| 20 | 5861, 5858, 5859 | WMI EventConsumer activity |
| 21 | 5861, 5858, 5859 | WMI EventConsumerToFilter activity |
| 22 | 1016, 3008, 3010, 3020 | DNS Query | | Noisy | Process that made the DNS query |
| 23 | | FileDelete | File Delete | | [Rule for .bat,.ps1,.xls, etc in downloads?!](https://www.blackhillsinfosec.com/wp-content/uploads/2021/01/image-15.png) |
| 24 | | ClipboardChange | Clipboard changed | | Use carefully. Anything copied/pasted may be archived IE admin creds. |
| 25 | | ProcessTampering | Process Tampering | | Detect MimiKatz? |
| 255 | | N/A | Sysmon error |

# Articles / Relevant Material Tied to Sysmon Event IDs + Notes:
1. Process Creation
2. Process Changed A File Creation Time 
    * MITRE:
      * [T1070.006 - Indicator Removal on Host: Timestomp](https://attack.mitre.org/techniques/T1070/006/)
3. Network Connections
    * MITRE:
      * [T1021 - Remote Services ](https://attack.mitre.org/techniques/T1021/)
4. Sysmon Service Change
5. Sysmon Service Change
    * Notes:
      * Uncommon. Images loaded/unloaded from _C:\Users_, _C:\Temp_, _C:\Windows\Temp_
6. Driver Loaded
    * Notes:
      * Uncommon. Further research required.
7. Image Loaded
    * Notes:
      * Shows instantiating process as well!
8. CreateRemoteThread
    * Notes:
      * Uncommon. Further research required.
9. RawAccessRead
    * Notes:
      * Uncommon. Further research required.
10. ProcessAccess
    * Other Resources:
      * [Cyber Wardog - Hunting for In-Memory Mimikatz with Sysmon and ELK - Part II (Event ID 10)](https://cyberwardog.blogspot.com/2017/03/chronicles-of-threat-hunter-hunting-for_22.html)
