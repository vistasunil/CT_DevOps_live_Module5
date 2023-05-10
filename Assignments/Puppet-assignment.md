<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> PUPPET ASSIGNMENT </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

#
</br>

## $`\textcolor{red}{\text{NOTE: USE UBUNTU 22.04 VIRTUAL MACHINES FOR ALL THE LABS}}`$

## Exercise 1: Puppet Manifest, Resource and Condition

### Complete below tasks as part of this exercise:

* Create a Puppet Manifest in production environment to perform below actions on slave nodes:
  * Install nginx first
  * Write the status of nginx installation as "nginx installed successfully!!" in a file **/tmp/sw_status.txt**
  * Install apache now
  * Append the same file **/tmp/sw_status.txt** with status of apache installation as "apache installed successfully!!"
  * Apache service must have failed to start because nginx is running on port 80. So, stop nginx service
  * Start apache service only if nginx is stopped

## Exercise 2: Puppet Variables

### Complete below tasks as part of this exercise:

* Create a Puppet Manifest in production environment to perform below actions on slave nodes:
  * Set a variable 'content' with some data to write in a file
  * Create a file using the data in **content** variable with below properties:
    * Name: /tmp/test_vars.txt
    * Owner: ubuntu
    * Group: ubuntu
    * Permissions: 0644
  * Now, take an array type variable **packages** containing list of packages to be installed. List should contain apache, nginx
  * Use this variable to first uninstall the packages installed in exercise 1 using one resource only
  * Add one more package mysql to array **packages**
  * Install all the software in **packages** using one resource only

## Exercise 3: Case Study

**You work for a Software Company. Recently the company got funding and they have decided to expand their server fleet. You have been designated the task for Configuration Management:**

* Assume the following infrastructure:
  * One Nginx Server
  * One Apache Server
  * One Puppet Master
* On Apache Server, we have to install docker and on the nginx server, we have to install Java.
* It sounds straightforward, but we do not know, which systems have what software installed on it.
* Using conditional statements, accomplish the above task.
* Also, for improving code readability, please make use of modules and classes.
* Validate and Package this module using pdk and save the tar file to /tmp folder for reusability.
