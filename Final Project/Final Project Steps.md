**Final Project Steps**

-------------------------------------------------------
# Samba File Server 
 **First I made a copy from my Virtual Machine to start my Project**

 **Then i Start to Install the Samba on my Virtual Machine**
   * I use the command " sudo apt-get install samba -y "

 **After the installing was done i start to Configure my share**
   * i use the Command " sudo nano /etc/samba/smb.conf "

**When the Configuration Page was Show up i started to configure the **WORKGROUP** and i changed to **WORKGROUPNAME**.** 

**Then i started to make a new Directory** 
  * i use the Command " sudo mkdir /data " 
  
 **Then i Create the group:**

  * i use the Command " sudo newgrp editors "

 **Then i Add myself to the group:**

  * i use the Command " sudo usermod -aG editors $USER "

 **Then i Change the ownership of the directory with the command:**

  * i use " sudo chgrp -R editors: /data "

 **Then i Give the group read and write permission to the new directory with the command:**

  * i use the Command " sudo chmod -R g+rw /data "

   **Finally now i'm ready to create the share.** 

Back at the /etc/smb.conf file, scroll to the bottom and add the following:

[DATA]
path = /data
valid users = @editors 
browsable = yes
writable = yes
read only = no

The configuration is simple:

    [DATA] the visible name of the share

    valid users = a group that can access the share. Even if a user has been added to Samba (with the smbpasswd command) they will not be able to access this share unless they are a member of the listed group

    path - the exact path of the share

    browsable - makes the share visible to the network

    writable - makes the share writable to authenticated users

    read only - sets the read-only option to no

**Then i Save and i close the file.** 

 i Restart Samba 

  * i use the Command " sudo systemctl restart smbd "

How to add a user to Samba

Now that everything's set up, you must also add users to Samba, otherwise they won't be able to authenticate. Even though a user has a legit account on the server, until they're added to Samba, it's a no-go.

 **After all that the first thing we have to do is add the user to Samba with the command:**

  * i use the Command " sudo smbpasswd -a USER "

Where USER is the user to be added.

**Next, enable the user with the command:**

* " sudo smbpasswd -e USER "

Where USER is the user to be enabled.

**Now i have Samba file server to the new share.**
