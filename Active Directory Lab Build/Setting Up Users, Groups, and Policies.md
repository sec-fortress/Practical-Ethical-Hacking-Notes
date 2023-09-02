Boot up your Window Server, which is our domain controller

- On the top right of the **server manager** application navigate to **Tools** then click on **Active Directory Users and Computers**

![](https://i.imgur.com/OKpvqAo.png)

- Now you should see a pop-up window, Click the drop down as shown below

![](https://i.imgur.com/Cq4NJdh.png)

- Once you see the drop down click **Users**, Note that the **Domain Admin** and the **Enterprise Admin** are the most important here

![](https://i.imgur.com/2Xjig96.png)

- Now Right-click on **MARVEL.local** and then select **New** then **Organizational Unit** 

![](https://i.imgur.com/FkrlPwL.png)

- Now you should see another pop-up, Under the Name: tab, Input **Groups** , then click **OK** 

![](https://i.imgur.com/C3uehsq.png)

![](https://i.imgur.com/JDoXHBd.png)

- Now move all the groups in the **Users** directory to **Groups** as seen in the GIF below , thereby leaving only the **Administrator** and **Guest** user account under the **Users** directory

![](https://i.imgur.com/BycPBDf.gif)

- Under the **Users** directory make a copy of the **Administrator** account, Just right click the **Administrator** account and click **Copy**

![](https://i.imgur.com/YEp5Hib.png)

- Now you should see a pop-up window, fill in what information you like in the highlighted area and hit **Next**

![](https://i.imgur.com/BpgfdkK.png)

- In the next windows type in any password you like, mine will be `Password12345!`, Then hit **Next**, also make sure to turn on the option **Password never expires**

![](https://i.imgur.com/MMC3JUa.png)

![](https://i.imgur.com/XWZbLll.png)

- Now we are going to create another service account for SQL , We are going to duplicate the **Administrator** account like we did for **tstark** , then set everything as illustrated in the picture below

![](https://i.imgur.com/PZyrVGa.png)

- Then on the next window set your password, mine is `MYpassword123#` also make sure that you set the password to **Password never expires**

![](https://i.imgur.com/KniRCHl.png)




