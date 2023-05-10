<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> PUPPET MODULES </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

## CREATING MODULES IN PUPPET

### Steps for Puppet Master

**Note: Make sure you have installed pdk during the install of puppet.**

### Step 1: Navigate to **/etc/puppetlabs/code/environments/production/modules/** folder

`cd /etc/puppetlabs/code/environments/production/modules/`

`sudo pdk new module my_module`

![image](https://user-images.githubusercontent.com/37858762/235783916-94556f03-7b8c-4557-9db2-5c41b7a49531.png)

### Step 2: You have successfully created the module. Change into the following directory **./my_module/manifests**. We next create a class in the module.

_Classes are named blocks of Puppet code that are stored in modules and applied later when they are invoked by name. You can add classes to a node's catalog by either declaring them in your manifests or assigning them from an external node classifier (ENC). Classes generally configure large or medium-sized chunks of functionality, such as all of the packages, configuration files, and services needed to run an application__._

`sudo pdk new class my_class`

![image](https://user-images.githubusercontent.com/37858762/235783952-6ae47bc8-75d2-4f4c-9591-123d09772640.png)

This will create two files; one of which we will be updating (_modules/my\_module/manifests/my\_class.pp )_.

### Step 3: Next, we add a resource to the class.

_A resource declaration adds a resource to the catalog and tells Puppet to manage that resource's state._

_When Puppet applies the compiled catalog, it:_ <br />
_1. Reads the actual state of the resource on the target system._ <br />
_2. Compares the actual state to the desired state._ <br />
_3. If necessary, changes the system to enforce the desired state._ <br />
_4. Logs any changes made to the resource. These changes appear in Puppet agent's log and in the run report, which is sent to the master and forwarded to any specified report processors._

Here we create a resource that ensures that a file, _/tmp/module\_test.txt_, exists with the content 'This file is created by a module' on each of the target systems. We update the class, _modules/my\_module/manifests/my\_class.pp_, to the following:

```
class my_module::my_class{
  file{'/tmp/module_test.txt':
    content => 'This file is created by a module',
    mode    => '0644',
  }
}
```

![image](https://user-images.githubusercontent.com/37858762/235784014-764597ef-ddc2-4c3a-8201-91f3015f9a10.png)

### Step 4:  **Validate the module:

`sudo pdk validate`

cd to the **my_module** directory of not already there, and pass the following command:

![image](https://user-images.githubusercontent.com/37858762/235784066-5fce1160-dc19-489e-87b0-f2bb9c8e58c8.png)

### Step 5: Now we need to designate which systems to apply the _my\_class_ class to by creating a site manifest; starting with an empty file _manifests/site.pp_.

_Puppet starts compiling a catalog either with a single manifest file or with a directory of manifests that are treated like a single file. This starting point is called the main manifest or site manifest._

In the site manifest, we include one or more node definitions.

_A node definition, also known as a node statement, is a block of Puppet code that is included only in matching nodes' catalogs. This allows you to assign specific configurations to specific nodes._

_Put node definitions in the main manifest, which can be a single site.pp file, or a directory containing many files._

_If the main manifest contains at least one node definition, it must have one for every node. Compilation for a node fails if a node definition for it cannot be found. Either specify no node definitions, or use the default node definition, as described below, to avoid this situation._

Here we want to declare (essentially applying) _my\_class_ to all systems (nodes); we update _manifests/site.pp. Navigate to directory /etc/puppetlabs/code/environments/production/manifests and add file site.pp with below contents:_

```
node default {
  include my_module::my_class
}
```

![image](https://user-images.githubusercontent.com/37858762/235784185-a89f3ec4-53d3-4c39-acec-229a95b594f1.png)

### Step 6: While Puppet agent, by default, is configured to apply updates every 30 minutes (runinterval = 1800), we can expedite an update by executing the following command as root on a system with a connected Puppet agent. Go to agent server and run below command to pull the changes:

`sudo /opt/puppetlabs/bin/puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235784225-1db2e795-9701-4eeb-90de-958840bd34cc.png)

_The output indicates that it applied our class and we can confirm the result by executing:_

![image](https://user-images.githubusercontent.com/37858762/235784261-d40b6f56-ba00-4387-8448-11870c5f5d03.png)

### Step 7: Module's Main Class

Here we explore using a number of classes from a module without having to explicitly include each one into a node definition. We do this by using a module's main class.

The init.pp class, if used, is the main class of the module. This class's name must match the module's name.

Let us start by creating a second class in the module; within the _modules/my\_module _folder, we execute:

`sudo pdk new class another_class`

![image](https://user-images.githubusercontent.com/37858762/235784298-ad45437b-f907-455f-955d-8bfd0a92b61b.png)

### Step 8: Update _modules/my\_module/manifests/another\_class.pp_ to:

```
# @summary A short summary of the purpose of this class
# A description of what this class does
# @example
# include my_module::another_class

class my_module::another_class {
  file { '/tmp/another':
    ensure  => 'present',
    content => 'Another Hello World',
    path    => '/tmp/another',
  }
}
```

![image](https://user-images.githubusercontent.com/37858762/235784355-3cf635f2-f3c7-42e2-89e9-e02caa54616e.png)

### Step 9: Next, we create the main class; within the modules/my\_module folder, we execute:

`sudo pdk new class my_module`

![image](https://user-images.githubusercontent.com/37858762/235784382-defed2e7-aa83-4f60-bdc2-9d2cdbdf859b.png)

**Things to observe:**

_The class is named the same as the module; my\_module_

_A file, modules/my\_module/manifests/init.pp, is created_

_We now update modules/my\_module/manifests/init.pp to include the other two modules:_

```
# @summary A short summary of the purpose of this class
# A description of what this class does
# @example
# include my_module

class my_module {
  include my_module::my_class
  include my_module::another_class
}
```

![image](https://user-images.githubusercontent.com/37858762/235784437-5d97de9b-a5ac-4ff8-b5a2-6391d12fc74e.png)

### Step 9: With this in place, we can now update _manifests/site.pp_ to. cd to directory /etc/puppetlabs/code/environments/production/manifests and update site.pp:

```
node default {
  include my_module
}
```

![image](https://user-images.githubusercontent.com/37858762/235784673-d6824bf7-602b-48bf-ab9d-90d5dae8bca5.png)

### Step 10: Pull the changes on agent:

`sudo /opt/puppetlabs/bin/puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235784701-b562f4e9-0aa1-410e-aa92-d94f48f96051.png)

With these changes, the systems with a connected Puppet agent will now (after the 30-minute update) have two files, _module\_test.txt_ and _another_, in the _/tmp_ folder. Again, we can expedite this by manually triggering an update.

### Step 11: Build module to package. The generated package will be place in pkg folder inside module directory itself.

_Packages are portable unit that can be shipped or published to puppet forge for distributed access:_

`sudo pdk build`

![image](https://user-images.githubusercontent.com/37858762/235784736-1bb6d41e-73cb-45e6-b219-6c10adc046fe.png)

### Step 12: Next, we will install the module by referring the tar.gz file from the last output. Since, here we are installing on same puppet server, so we will remove the existing my\_module folder to /tmp:

`sudo /opt/puppetlabs/bin/puppet module install /tmp/my_module/pkg/cloudtrain-my_module-0.1.0.tar.gz`

![image](https://user-images.githubusercontent.com/37858762/235784767-756b69f0-d4cf-4dea-8686-3f263684aed2.png)

### Step 13: Finally, go to the main manifest file in **/etc/puppetlabs/code/environments/production/manifests/site.pp and** include the following code:

```
node default{
  include my_module
}
```

![image](https://user-images.githubusercontent.com/37858762/235784832-cede70ec-9c91-4fdf-92ae-4cea252163c0.png)

### On Puppet Agent

### Step 14: Remove existing files in /tmp (if any) and execute the following command to pull the changes from installed module:

`sudo /opt/puppetlabs/bin/puppet agent --test`

![image](https://user-images.githubusercontent.com/37858762/235784865-283a8d5b-44f2-403b-b96e-66b4d86cf870.png)

### Step 15: Verify the configuration change by checking /tmp/module\_test.txt and /tmp/another

![image](https://user-images.githubusercontent.com/37858762/235784892-1db8690b-f2be-4acd-a409-6c8514f55d10.png)

