
- Create a New virtual Machine, Using VM ware, you can do the same if you use VirtualBox

![](https://i.imgur.com/GDbz3XZ.png)

- Browse to where the windows server is located at and select it then click Next

![](https://i.imgur.com/YWNblFb.png)

- Hit Next here too and Click `Yes`

![](https://i.imgur.com/KjtchDk.png)

- Keep Hitting `Next` to you get to this screen, Make sure the **Power on this virtual machine after creation** is unchecked then click `Finish`

![](https://i.imgur.com/rjYcjUM.png)

- You should now see that the virtual machine has been created, click **Edit virtual machine settings** 

![](https://i.imgur.com/WxxHvoa.png)

- If you see a `Floppy Disk` option make sure to remove it to avoid future errors , Also tweak the **Hard Disk** and **Memory** option to what ever suite you, Making sure that **Hard Disk** has nothing less than **60gb** and the **Memory** to **2gb**, When done click **OK**

![](https://i.imgur.com/T2LWFhM.png)

- Now **Play virtual machine** and if you are asked to **click any key to boot from CD**, Make sure to do that.

![](https://i.imgur.com/fvljrcn.png)

- You will be presented with this screen, Hit **Next** and then **Install Now**

![](https://i.imgur.com/gdRNkYo.png)

- Select the **Second Choice** on the screenshot and click **Next**

![](https://i.imgur.com/YhlFuNL.png)

- Accept The **Software License Terms** and Hit **Next** 

![](https://i.imgur.com/TnqSOYV.png)

- Select **Custom** here

![](https://i.imgur.com/atutfrA.png)

-  Click **New**

![](https://i.imgur.com/kpXAqF4.png)

- Click **Apply**

![](https://i.imgur.com/0H7tD6T.png)

- Click **Ok**

![](https://i.imgur.com/HfTPFU1.png)

- Then click **Next**

![](https://i.imgur.com/Gihgtz7.png)

- Wait for the Installation process to finish and you should get a reboot

![](https://i.imgur.com/O5mvzy3.png)

- Just click **Enter** on your keyboard

![](https://i.imgur.com/SQ0NHs1.png)

- Then wait for this Initialization to finish

![](https://i.imgur.com/d373quO.png)

- Type in a Password , in my case it is `P@$$w0rd!` and hit **Finish** 

![](https://i.imgur.com/gmrMgkb.png)

- Hit the Button highlighted in the screen shot or do **Ctrl+Alt+Del** as asked to and type in your Password you created earlier, in the next section.

![](https://i.imgur.com/CRr29Pn.png)

![](https://i.imgur.com/lnIIKso.png)

- Click **Yes** and then **cancel** 

![](https://i.imgur.com/A8LfaEt.png)

- Click the windows search bar and search with the keyword `Rename` , then select the first result

![](https://i.imgur.com/e5Bc0hE.png)

- Then click **Rename this PC** and rename the PC to {anything}-DC , Mine will be `HYDRA-DC` , After this the system will ask for a reboot, It okay, Click **Restart Now** and **Continue**

![](https://i.imgur.com/8Uv4I1a.png)

![](https://i.imgur.com/6MkAFoC.png)


As usual login with the Password you used to create the account and let continue

- On the Top Right Menu click **Manage** then **Add roles and features**  

![](https://i.imgur.com/IstBvqd.png)

- Once you get this page below, keep clicking **Next** till you get to the next image

![](https://i.imgur.com/zJCgGSY.png)

![](https://i.imgur.com/nAfCfMN.png)

- Now select **Active Directory Domain Services** under the Roles tab, you should get a pop-up, Click **Add Features**

![](https://i.imgur.com/yJt2Gwy.png)

- You should now get this page Keep clicking **Next** till you get to the next page in the image below

![](https://i.imgur.com/sfrQedd.png)

- Keep clicking **Next** till you get to the next page in the image below, Make sure to check the **Restart the destination server automatically if required** box and click **Yes** on the pop-up then click **install**

![](https://i.imgur.com/7oZGcVt.png)

- This will install all Active Directory Domain Services (ADDS) 

![](https://i.imgur.com/gmaXLOS.png)

- Once the above step is done, Click **Promote this server to a domain controller**

![](https://i.imgur.com/KOmzquC.png)

- Then **Add a new forest**, since we don't have one yet, The **Root domain name** could be {ANYTHING}.local , then clcik **Next**

![](https://i.imgur.com/uS58I3K.png)


- Now type in a password in the highlighted area, It could still be the same password for the MARVEL domain controller, In my case it will be `P@$$w0rd!` , then click **Next**

![](https://i.imgur.com/tw8n5EU.png)

- Hit **Next** here again, then wait for few seconds

![](https://i.imgur.com/i4VTMJ4.png)

- Keep hitting **Next** till you get to the second screenshot below which is going to do a prerequisites check

![](https://i.imgur.com/5WN0dVC.png)

![](https://i.imgur.com/6ZbdFyN.png)

- Then click **Install** (This should take a while), After this is done, it will automatically restart the system, So type in your password as usual

![](https://i.imgur.com/jn5NuII.png)

- Once again Click **Manage** on the top right page and select **Add roles and features**

![](https://i.imgur.com/8rus4U8.png)

## Setting Up Certificate Services

- Now keep clicking **Next** till you get to the page in the second image below

![](https://i.imgur.com/rQLBbXz.png)

![](https://i.imgur.com/DYScNJn.png)

- Then select **Active Directory Certificate Services** under **Roles** and you should see a pop-up window like the one below, Click **Add features**

![](https://i.imgur.com/O8H8kRN.png)

- Click **Next**

![](https://i.imgur.com/Jq2RBHL.png)

- If you wanna add features then go ahead and add them, I will be leaving this as default, so click **Next** to continue

![](https://i.imgur.com/dNy7tKy.png)

- Keep clicking **Next** till you get to the page below

![](https://i.imgur.com/xasTZqz.png)

- Check the **Restart the destination server automatically if required** box and click **Yes** on the pop-up then click **install** , It is gonna start the installation of the **Active Directory Certificate Services**

![](https://i.imgur.com/kuhEQd7.png)

- Once the above step is done , Click the highlighted area on the image below

![](https://i.imgur.com/WjFx8jB.png)

- Once you get the pop-up hit **Next**

![](https://i.imgur.com/GHLUDVf.png)

- Then on the next page make sure to check the **Certification Authority** box cos' it is unchecked by default then hit **Next**

![](https://i.imgur.com/PNWIYT6.png)

- Keep hitting **Next** till you get to the page below then select the validity to whatever amount of years you like, Mine would be `99`, then click **Next**

![](https://i.imgur.com/0GUBnic.png)

- Keep hitting **Next** again 😆 till you get to the page below , then click **Configure**

![](https://i.imgur.com/kY6EsjK.png)

- Wait for few seconds and click **Close**

![](https://i.imgur.com/pEUq0nw.png)

You can now **Re-Boot** the server and that will be all on setting up a Domain controller




