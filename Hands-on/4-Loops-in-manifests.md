<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> LOOPS IN MANIFESTS </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

## USING LOOPS IN MANIFESTS

### Steps for Puppet Master

### Step 1: Change the directory to **/etc/puppet/code/environments/production/manifests**

`cd /etc/puppet/code/environments/production/manifests`

### Step 2: Enter the following text:

`sudo vim site.pp`

```
node default{
  $packages= ['apache2','mysql-server']
  
  package{$packages:
    ensure => installed,
  }
}
```

![image](https://user-images.githubusercontent.com/37858762/235779753-bbb64ec1-7fa9-4f04-9848-f25af37ad63d.png)

### On Puppet Agent:

### Step 1: Execute the following command:

`sudo /opt/puppetlabs/bin/puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235779840-590b5a8b-1769-40d7-b537-d3200406031a.png)

### Step 2: Verify the installation by going to the browser with Agent's IP address and mysql service status

![image](https://user-images.githubusercontent.com/37858762/235779917-44d07434-8884-4de4-a2b6-056c4695c0da.png)

![image](https://user-images.githubusercontent.com/37858762/235779947-9476de8b-cdba-4de8-8db1-348ebd0de8dd.png)
