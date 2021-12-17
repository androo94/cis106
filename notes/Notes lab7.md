## Managing User Accounts
---------------------------------------------

* Managing user accounts involves adding, modifying and deleting user accounts.
  
* The add user accounts we use the **usedadd** or **adduser** command
  
* To modify user's information we use the **usermod** program

* To Delete a users we use the **userdel** program

* Run the command **adduser** followed by the username (to add a user in ubuntu)

* Run the Command **userdel** followed by the username (to delete a user in ubuntu)

    * u need to pass the -r option for the command to delete the user and its home directory.

* The management of users in all linux system is governed by multiple files.

The/etc/login.defs file
  * it contains directives for use in various shadow password.
  
The/etc/passwd file
  * stores informations about every account in a linux system
  * each line in the passwd file represents a user. when an accounts is created.
  
## Creating a user with useradd
-------------------------------------------------
  * **-md** are the options needed for adding a hom directory to the new user.
  * **/home/student** is the new user's home directory.
  * **-s** used for specifying the user's login shell.
  * **/bin/bash** the new user's login shell.