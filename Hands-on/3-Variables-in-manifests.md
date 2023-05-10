<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> VARIABLES IN MANIFESTS </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

## USING VARIABLES IN MANIFESTS

### Steps for Puppet Master

### Step 1: Change the directory to **/etc/puppet/code/environments/production/manifests**

`cd /etc/puppetlabs/code/environments/production/manifests`

`sudo vim site.pp`

### Step 2: Enter the following text:

```
node default{
  $text= "hello world\n"
  file{'/tmp/helloworld.txt':
    content => $text,
    mode    => '0644',
  }
}
```

![image](https://user-images.githubusercontent.com/37858762/235778815-2f87eead-48f7-4a24-8c7b-dc443616be38.png)

### On Puppet Agent

### Step 1: Execute the following command:

`sudo /opt/puppetlabs/bin/puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235778889-71ea4088-786a-4e75-8f41-a12facd83272.png)

### Step 2: Verify the installation and file by going to the browser, with agent's ip address. Also check /tmp/hello.txt

`cat /tmp/helloworld.txt`

![image](https://user-images.githubusercontent.com/37858762/235778951-19452e27-54f2-4217-8d51-f274a7d13ba3.png)
