Go ahead and start up all virtual machines (The 2 windows OS and your Domain controller)

![](https://i.imgur.com/8IW9Cd7.png)

Now we need to join the 2 windows server with our domain controller, Let first of all start with user **frankcastle**.

- Navigate to the Network icon on the **Task bar** and click **Network and internet settings**

![](https://i.imgur.com/hokvKkE.png)

- You should now see the settings window, Scroll down and click **Change adapter options**

![](https://i.imgur.com/L2Kn3Pg.png)

- You should see another **Network connections** tab, Double click **Ethernet0** and click properties on the next pop-up

![](https://i.imgur.com/Z1lpzAz.png)

- You should now see another window, double click the **(TCP/IPV4)** item to bring up another pop-up window

![](https://i.imgur.com/SMDrVwj.png)

- Now click **Use the following DNS server addresses** and add the IP address of your domain controller to the the **preferred DNS server** box, then click **OK** (You can use **ipconfig** to check for the IP of your DC in command prompt)

![](https://i.imgur.com/I1aF2G4.png)

- After clicking **OK** on the previous window, you will see another underlying window, make sure to click **OK** again to save the settings

![](https://i.imgur.com/YGRlvBb.png)

**MAKE SURE TO REPEAT THIS SAME STEPS FOR THE USER "PETERPARKER"**
#### Joining the domain

We can go back to the user "frankcastle" and on the windows search bar, type in the keyword **domain** ,  you should see **Access work or school** settings, click it.

![](https://i.imgur.com/N8F08Dt.png)

On the next pop-up window click **Connect**

![](https://i.imgur.com/lkFjcdk.png)

Since we are joining the domain we don't need to input any Email , click the Alternate action, **join this  device to a local Active Directory domain**

![](https://i.imgur.com/NGTOgco.png)

Now we can type in our Domain name, in my case it is **MARVEL.local** and immediately you should see another pop-up window asking for a `Username` and `Password`

![](https://i.imgur.com/BQJGPUS.png)

![](https://i.imgur.com/r345DzN.png)

Now the User name is `administrator` and password is `P@$$w0rd!` , you should remember what the username and password is

On the next window is the **Add account** , make sure to set the account type to **Administrator** then hit **Next** and then **Restart now**.

![](https://i.imgur.com/JbuTTwE.png)

**NOW GO AHEAD AND DO THIS EXACT SAME THING FOR USER "PETERPARKER"**



Now we can login to our Domain Controller, Navigate to serever manager then **Tools**
