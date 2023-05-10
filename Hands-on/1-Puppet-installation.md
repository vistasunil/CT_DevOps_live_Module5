<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> PUPPET INSTALLATION </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

## PUPPET INSTALLATION

### Installing Puppet Master

### Step 1: Run the following commands for installing Puppet Master

```
sudo apt-get update
sudo apt-get install wget
wget https://apt.puppetlabs.com/puppet6-release-bionic.deb
sudo dpkg -i puppet6-release-bionic.deb
sudo apt update
sudo apt-get install puppetserver
```

Installing Puppet Development Kit for modules development:

```
wget https://apt.puppet.com/puppet-tools-release-bionic.deb
sudo dpkg -i puppet-tools-release-bionic.deb
sudo apt-get update
sudo apt-get install pdk
```

### Installing Puppet Agent

### Step 2: Run the following commands for installing Puppet Agent

```
sudo apt-get update
sudo apt-get install wget
wget https://apt.puppetlabs.com/puppet6-release-bionic.deb
sudo dpkg -i puppet6-release-bionic.deb
sudo apt update
sudo apt-get install puppet-agent
```

### Configuring Puppet Master

### Step 3: Make changes to the hosts file which exists in /etc/hosts. And add the Puppet Master IP address along with the name **puppet**

`sudo vim /etc/hosts`

![image](https://user-images.githubusercontent.com/37858762/235773037-64757233-52f4-4769-9517-8e951babcbc9.png)

### Step 4: Generate a root and intermediate signing CA for Puppet Server. Switch to **root** account and run below command:

`puppetserver ca setup`

Start the Puppet Server service:

`sudo systemctl start puppetserver`

Or

`sudo service puppetserver start`

### Step 5: Memory Allocation: By default, Puppet Server is configured to use 2GB of RAM. However, if we want to experiment with Puppet Server on a VM, we can safely allocate as little as 512MB of memory. To change the Puppet Server memory allocation, we can edit the init config file, /etc/default/puppetserver:

`sudo vim /etc/default/puppetserver`

**Change JVM size as below**

`JAVA_ARGS="-Xms512m -Xmx512m"` **//Update this only if you want to change java memory allocation**

`sudo systemctl restart puppetserver`

![image](https://user-images.githubusercontent.com/37858762/235773266-a471818f-e5c2-4283-a184-ca52a3d04c4f.png)

Replace 2g with the amount of memory you want to allocate to Puppet Server. For example, to allocate 1GB of memory, use JAVA\_ARGS="-Xms1g -Xmx1g"; for 512MB, use JAVA\_ARGS="-Xms512m -Xmx512m".

![image](https://user-images.githubusercontent.com/37858762/235773356-24f265f6-edc2-4adb-8b39-aafad4cc8fba.png)

### Step 6: Update /etc/puppetlabs/puppet/puppet.conf and add the dns_alt_names line to the section [main], replacing puppet.example.com with our own FQDN:

```
[main]
server=puppet
```

![image](https://user-images.githubusercontent.com/37858762/235773373-69db21d5-60f4-4b2a-a153-55a8817bff54.png)

### Step 7: Start Puppet server and enable it to start on boot time with the following command:

`sudo systemctl start puppetserver`

`sudo systemctl enable puppetserver`

![image](https://user-images.githubusercontent.com/37858762/235773396-049f4f6b-8f4c-468a-b1df-6ae87f3ca521.png)

If service already started, then restart it:

`sudo systemctl restart puppetserver`

![image](https://user-images.githubusercontent.com/37858762/235773522-e581cad8-6839-480d-aca7-76a5981aa1da.png)

Check the puppet version installed:

`puppetserver --version`

![image](https://user-images.githubusercontent.com/37858762/235773560-8f7f423c-a9d5-473c-be02-205741207170.png)

### Configuring Puppet Slave

### Step 9: Add the entry for Puppet Master in /etc/hosts

![image](https://user-images.githubusercontent.com/37858762/235773591-92199f6f-a60c-4d9b-bad8-9cb0afe85098.png)

`sudo /opt/puppetlabs/bin/puppet resource service puppet ensure=running enable=true`

![image](https://user-images.githubusercontent.com/37858762/235773652-a1cf2e87-7a6e-4f7e-af71-9030555c3779.png)

### Step 10: Start the puppet service: 

![](RackMultipart20230502-1-rwf2wg_html_e5a3510792b8b01a.png)

```
[main]
server = puppet
```

### Step 11: Add the server value to the [main] section of the node's /etc/puppetlabs/puppet/puppet.conf file, replacing puppet.example.com with the FQDN of our Puppet master: ![Shape19](RackMultipart20230502-1-rwf2wg_html_ad5fada4d777a516.gif)

![image](https://user-images.githubusercontent.com/37858762/235773737-2043ccc9-bad4-4828-b3dd-6ac8285fa1fe.png)

### Step 12: Finally start the Puppet agent by using the following command. Also, enable the service, so that it starts when the computer starts

`sudo systemctl start puppet`

`sudo systemctl enable puppet`

![image](https://user-images.githubusercontent.com/37858762/235773772-b1b003b3-7205-4490-8d16-fc76b5071563.png)

### On Master:

### Step 13: Sign certificates on the certificate authority (CA) masterType the following command:

`sudo /opt/puppetlabs/bin/puppetserver ca list`

![image](https://user-images.githubusercontent.com/37858762/235773818-9d8b5dc1-adae-4d43-b4d1-2bb9c896f4f5.png)

### Step 14: Finally, sign the listed certificate using the following command:

`sudo puppetserver ca sign --certname <certName>`

Or, run below to sign all requested certs:

`sudo /opt/puppetlabs/bin/puppetserver ca sign --all`

![image](https://user-images.githubusercontent.com/37858762/235773838-8aef9aa6-60da-4e9a-b949-a2eaf5da408a.png)

### On Agent:

### Step 15: Test the agent connectivity

`sudo /opt/puppetlabs/bin/puppet agent -t`

![image](https://user-images.githubusercontent.com/37858762/235773855-9f0431bc-c81b-4170-ae6f-9f3a3e7ac2da.png)

You are now ready to use the Puppet cluster!
