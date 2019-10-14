---
title: Quick Start for ownCloud
layout: 
---

# Quick Start for ownCloud

This guide describes how to get started quickly with ownCloud. It is intended for both ownCloud administrators and end users. 

## About ownCloud

ownCloud provides secure storage and access control for files on a host server, either in the cloud or on-premises. Through ownCloud client applications, users with appropriate permissions can access those files for sharing and synchronizing on their local computers or mobile devices. 

* ownCloud server runs on Linux.
* ownCloud client applications run on Linux, Microsoft Windows, Mac OS, Android, and Apple iOS.

## ownCloud for Administrators 

The sample environment for procedures in this guide consists of ownCloud Server running as a VM (virtual machine) in VirtualBox on a Windows host operating system. Details about these and other components are as follows:

* **ownCloud Server 10.2.1 appliance**, built on UCS (Univention Corporate Server), preconfigured with an Apache2 web server, PHP (Hypertext Preprocessor) programming language, and MySql database management system. UCS is a Linux-based server operating system that enables central administration for servers, services, clients, and users.
* **Oracle VM VirtualBox 6.0.1**, a cross-platform virtualization application that allows Linux to run on a Windows machine. 
* **Microsoft Windows 10 Home (64-bit)** 
* **DHCP** (Dynamic Host Configuration Protocol) server to automatically configure IP addresses and other network settings 
* **Internet** access

 Overall steps are to:
 1. Download and install VirtualBox.
 1. Download and install the ownCloud server appliance.
 2. Configure host and domain settings.
 3. Add user accounts.  
 
### Download and install VirtualBox

 1. In your browser, go to <https://www.virtualbox.org/wiki/Downloads>.
 2. Under **VirtualBox 6.0.10 platform packages**, click **Windows hosts**.
 3. Download and save the file _VirtualBox-6.0.10-132972.exe_.
 4. Double-click _VirtualBox-6.0.10-132972.exe_ 
 5. Follow the setup instructions to install VirtualBox.  

### Download the ownCloud server appliance

 1. In your browser, go to <https://owncloud.org/download/>.
 2. Under **Table of contents > ownCloud Server**, click **Appliance**.
 3. Click **Download VirtualBox image**.
 3. Download and save the file _Univention-App-owncloud-virtualbox.ova_.  

### Import the ownCloud server appliance

 1. In VirtualBox, click **File > Import Appliance**.
 2. Locate and select the downloaded file _Univention-App-owncloud-virtualbox.ova_.
 3. Click **Import**.
	
	After the file import completes, the list of VMs in VirtualBox includes _UCS 4.4-with-owncloud_.

### Install and configure the ownCloud appliance

 1.	In VirtualBox, select the _UCS 4.4-with-owncloud_ VM and click **Start**.
	
	The ownCloud installer wizard opens.
	
 2.	Complete the ownCloud Appliance setup wizard, as follows:  
	a. **Localization settings** -- Specify your language and a city near you to automatically determine the timezone, locale, and language for keyboard layout.  
	b. **Domain and network configuration** -- Specify network settings either automatically or manually.  

	**Note**: To use a proxy server as an intermediary between end users and the internet, click the **configure proxy settings** link. Specify the address of the HTTP proxy, including the port number, for example:  

	> http:<span></span>//proxy.domainname.intranet:8080

	c. **Account information** [specify]  
	d. **Host settings** [specify]
	
 3.	To confirm your configuration settings, click **Configure System**.
 4.	Click to accept the software license and then click **Continue**.

	When the installation completes, the _ownCloud Appliance_ screen appears.

	**Note**: Record the IP address shown in the _ownCloud Appliance_ screen because you need it for the next step.

### Activate the ownCloud appliance in UCS

 1. In your browser, navigate to the IP address for the ownCloud appliance.
	* If you see a message that your connection is not private, click **Advanced**, and then click the link to proceed to the IP address you specified.
	* If a message about an untrusted certificate appears, click **Allow** and enter your password, if necessary.

	The _License request for ownCloud Appliance_ dialog box appears.

 2. Type your email address and click **Request Activation**.

	The _Activation of ownCloud Appliance_ dialog box appears.

 3. Follow instructions to obtain a license key for activating the ownCloud appliance in UCS.  
	a. Click **Upload License File**.  
	b. Locate and select the downloaded license file and click **Open**.  
	c. To complete successful activation, click **Finish**.  

	The *Univention Portal* opens, which provides a central view of all services available in your UCS domain.

 4. Click **UCS System and domain settings**.
 5. Log in with your Administrator account credentials.

	The UMC opens, from which you can centrally manage all system components of your virtual environment.

### Add users

In UMC, you can manage LDAP user accounts for the ownCloud server.

 1.	In your browser, open the Univention Portal by navigating to the IP address for the ownCloud appliance. For example:

	[SAMPLE URL]

 2. [click to open user management]
 3. [add a user and repeat as needed]

### Next steps

 [test your configuration]
 [communicate URL/IP:8080 to your users, with information provided under "ownCloud for End Users"]

## ownCloud for End Users

With the ownCloud desktop client or mobile app, you can connect and access files on the ownCloud server.

 1. In your browser, go to <https://owncloud.org/download/>.
 2. Under the **Table of contents**, locate the ownCloud desktop client or mobile app for your environment:  
 	* [dt clients]  
	* [mobile apps]  
 3. [client setup]
 4. [connect to server]

	If you have a problem connecting to the server, first make sure you have the correct URL. Otherwise, try connecting through a proxy server with a specific port number, for example:

	> http:<span></span>//proxy.domainname.intranet:8080

	where, **:8080** specifies the port number.

For more information, contact your ownCloud administrator.

