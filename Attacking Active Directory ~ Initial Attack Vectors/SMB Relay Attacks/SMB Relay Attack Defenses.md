![](https://i.imgur.com/BVG3x91.png)

### Evaluation of Mitigation Strategy’s Effectiveness

The administrators should restrict NTLM authentication on the domain. To do that they should follow the steps below:

On the domain controller, by using **Win+R** type **gpedit.msc** that will bring on the **Local Group Policy Editor**.

Under **Local Computer Policy**, navigate to `Computer Configuration → Windows Settings → Security Settings → Security Options`.

On the right side search to find, the policy called **Network Security: Restrict NTLM: NTLM authentication in this domain**.

Double click on that policy and at the pop-up Window on the **Local Security Setting** tab using the dropdown menu select **Deny All**. [6](https://dimitrios-tsarouchas.tech/posts/Active-Directory-SMB-Relay-Attack/#6)

![Open-Group-Policy-Management-Editor](https://dimitrios-tsarouchas.tech/assets/img/Open-Group-Policy-Management-Editor.png)_Open Group Policy Management Editor_

![Deny-NTLM-authentication-in-this-domain](https://dimitrios-tsarouchas.tech/assets/img/Deny-NTLM-authentication-in-this-domain.png)