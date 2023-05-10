<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> PUPPET MANIFESTS </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

## CREATING A MANIFEST

### Steps for Puppet Master

### Step 1: Change the directory to **/etc/puppetlabs/code/environments/production/manifests**

`cd /etc/puppetlabs/code/environments/production/manifests`

`sudo vim site.pp`

```
node default{
  package{'nginx':
    ensure => installed,
  }

  file{'/tmp/status.txt':
    content => "nginx installed",
    mode    => '0644',
  }
}
```

![image](https://user-images.githubusercontent.com/37858762/235777662-746d7bd3-b69b-4f39-8293-3db7a431f5cf.png)

### Step 2: Enter the following text:

### On Puppet Agent

### Step 1: Execute the following command:

`sudo puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235777718-a814051d-5280-4711-86b8-9f59fad6c57b.png)

### Step 2: Verify the installation and file by going to the browser, with agent's ip address. Also check **/tmp/status.txt**

![image](https://user-images.githubusercontent.com/37858762/235777796-9741b8c0-3e9a-43c1-a1fa-eed0967cc9c7.png)

![image](https://user-images.githubusercontent.com/37858762/235777820-b0345acd-9aba-4d39-ad3a-f7be459e4b08.png)

![image](https://user-images.githubusercontent.com/37858762/235777856-a8618a6c-4ff7-4f32-bcd0-7a276582f7a7.png)
