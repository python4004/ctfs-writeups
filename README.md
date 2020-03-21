# angstromCTF 2020
### This is our writeups for ångstromCTF 2020.
![angstrom-3e0d6c871da7786e59fcc988735f4f5ded75aab5fac89f538291b3ef033801eb](https://user-images.githubusercontent.com/36403473/77215806-d4b45380-6b1e-11ea-8853-b9539e6bc4d0.png)

i participated in ångstromCTF 2020 with my awesome team P1rates as python_4004 & my dude mokey  . This is our writeups about some challenges we solved during the competition.

## Web challenges 
### Git Good
 Noting the name of the challenge, I think the system is based on git mangement system 
 But I have to make sure first , so i will use dirb tool
![dirb](https://user-images.githubusercontent.com/36403473/77215204-85205880-6b1b-11ea-9ca2-a46a3b8c8347.png)

now lets try to download git files 
to do that open your terminal and write 
git clone +the link of the challenge 
##### git clone https://gitgood.2020.chall.actf.co/.git 
![Screenshot from 2020-03-21 02-37-29](https://user-images.githubusercontent.com/36403473/77215565-5f944e80-6b1d-11ea-9f41-b7f8d0feba48.png)
The first thing I thought about was looking at the log file
##### <span style="background-color: #FFFF00">git log -p</span>
![Screenshot from 2020-03-21 02-41-08](https://user-images.githubusercontent.com/36403473/77215657-037dfa00-6b1e-11ea-8edf-e4d6b2588f11.png)
yup i found the flag 
##### actf{b3_car3ful_wh4t_y0u_s3rve_wi7h}
### Consolation
