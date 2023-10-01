## **Overview**

- Group Policy preferences allow admins to create policies using embedded credentials.
- These credentials were encrypted and placed in a "cPassword".
- The key was accidentally released.
- patched in `MS14-025`, However the `MS14-025` patch does not apply to GPP passwords embedded prior to the patch.
- STILL RELEVANT ON PENTEST

## **Using Metasploit**

```powershell
1 meterpreter > background
2 msf > use auxiliary/scanner/smb/smb_enum_gpp
```

Set the backgrounded session and run it


## **Mitigation**


![](https://i.imgur.com/KYhpTjM.png)

