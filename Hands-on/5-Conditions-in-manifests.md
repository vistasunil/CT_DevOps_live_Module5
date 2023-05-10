<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> CONDITIONS IN MANIFESTS </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

## USING CONDITIONS IN MANIFESTS

### ONLYIF

### Steps for Puppet Master:

### Step 1: Change the directory to **/etc/puppet/code/environments/production/manifests**

`cd /etc/puppet/code/environments/production/manifests`

`sudo vim site.pp`

### Step 2: Enter the following text:

```
node default{
  exec{'Conditions':
    command => '/bin/echo "Apache is installed" > /tmp/software.txt',
    onlyif  => '/bin/which apache2',
  }
}
```

![image](https://user-images.githubusercontent.com/37858762/235781257-8ad97cf9-bae6-484a-88f4-691b3cb4fb35.png)

### On Puppet Agent:

### Step 1: Execute the following command:

`sudo /opt/puppetlabs/bin/puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235781357-f37e6bdd-f12e-470a-ba3d-b2d19a8bd6b4.png)

### Step 2: Verify the file by going to /tmp/software.txt

`cat /tmp/software.txt`

![image](https://user-images.githubusercontent.com/37858762/235781381-bafd387c-32d2-4b9f-915b-fa9ea10caeba.png)

### UNLESS

### Steps for Puppet Master

### Step 1: Change the directory to **/etc/puppet/code/environments/production/manifests**

`cd /etc/puppet/code/environments/production/manifests`

`sudo vim site.pp`

### Step 2: Enter the following text:

```
node default{
  exec{'Conditions':
    command => '/bin/echo "php is not installed" > /tmp/software.txt',
    unless  => '/bin/which php',
  }
}
```

![image](https://user-images.githubusercontent.com/37858762/235781565-55a9169c-ed5b-46a4-8bf7-de6a33e2ed77.png)

### Steps for Puppet Agent

### Step 1: Execute the following command:

`sudo /opt/puppetlabs/bin/puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235781729-3b3d3c5d-346a-4e48-a409-ccbdbef98ac7.png)

### Step 2: Verify the file by going to /tmp/software.txt

![image](https://user-images.githubusercontent.com/37858762/235781743-aa92c1bb-c7b2-44d3-a750-44995c99ea3a.png)
