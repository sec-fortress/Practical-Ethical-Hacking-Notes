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

![](https://i.imgur.com/4FnuOsr.png)

- Now **Double-click** on the **SQL Service** and on the description input **The password is MYpassword123#**, The reason why we are doing this is because this is a vulnerable lab and again some some users still do this thinking they are the only one that can see the description, meanwhile every valid user can :)

![](https://i.imgur.com/ji4ng2P.png)

- Now we need to create a couple of other Users to utilize in this environment, You can click anywhere on the white space then select **New** in the drop down select **User**

![](https://i.imgur.com/90jMy7j.png)

- You should now see the pop-up as shown below, it is time to link the two users we created (THEPUNISHER and SPIDERMAN), This will be for THEPUNISHER, so fill in the details as shown below

![](https://i.imgur.com/ZejJks4.png)

- You will get the password screen next, i will be using `Password1` as my password since it is the same password i used to create the account, also make sure to set the Password policy to **Passwords Never Expires**

![](https://i.imgur.com/tRXjVpm.png)

- Make another user called **Peter Parker** (SPIDERMAN) and repeat these same steps setting the password to `Password1` and never expires, Therefore just right click on the **Frank Castle** account and hit **copy**

![](https://i.imgur.com/J2F207J.png)

- Fill in the required fields as shown below

![](https://i.imgur.com/i42ACYQ.png)

- Set the password policy to **Password never expires**

![](https://i.imgur.com/pAvGnkV.png)

![](https://i.imgur.com/D7aFRQY.png)

- We need to create a file share that we can abuse later on, so navigate to the **Server Manger >> Dashboard**

![](https://i.imgur.com/ktPTYXM.png)

- Once you get a pop-up click **Shares**

![](https://i.imgur.com/soFsZa1.png)

- 



