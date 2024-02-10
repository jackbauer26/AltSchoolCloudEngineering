Step 1: Change into the home directory 

Cmd -> ```cd /home``` 

	 
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/5a2464fa-dbc7-403b-a71f-2f4cb4158148)


 

Step 2: Create the altschool folder 

Cmd -> `sudo mkdir altschool`

	 
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/becdf17b-2207-4355-b62f-fc864e556d7c)

 

Step 3: Create other sub-directories 

Cmd -> `sudo mkdir code test personal misc` 

	 
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/c8b1732c-679f-4ea6-8c98-418c8286345c)

 

Step 4: Change to the test sub-directory via the absolute path 

Cmd -> `cd /home/test` 

 ![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/ea35f64e-0dcd-42d5-a942-32d249c6b434)


Step 5: change into the test sub-directory via the relative path 

Cmd -> `cd  ./test` 

              	 
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/c4d11074-dafc-4dc5-9c5a-8f969eecaded)

 

Step 6: create a file called fileA with some content 

Cmd -> `echo “Hello A” > fileA` 

	 
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/e3ccf5e9-d703-410f-b372-a9d3a37425f2)

 

Step 7: Create an empty file in the misc directory and populate it with dummy content 

Cmd -> `echo “Thisis the content of file B” > fileB` 

![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/8d737f91-8c94-437d-bf68-8e3ccee90383)
	 

 

Step 8: Copy the contents of fileA into fileC 

Assumption: I am in the personal directory 

Cmd -> `cp ../test/fileA ../testfileC` 

 ![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/193d7af9-fa8d-47eb-902e-83f10669356e)


 

Step 9: Move contents of fileB into fileD 

Cmd -> `cd ./misc && mv fileB fileD` 

![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/58a6c45f-424d-422e-8fa6-8c86dc4032e7)
	 

 

Step 10: Create a tar archive called misc.tar 

Cmd: `tar –cf misc.tar misc` 

![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/a0958b1c-7da5-4e0f-a76b-790896b0a976)
	 

 

Step 11: Compress the tar file in step 10 above 

Cmd: `tar –czf misc.tar.gz misc` 

                  
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/cacb1a1f-0dc8-4de0-90bc-22c0f5616835)

 

Step 12: Create a user and force the user to change their password upon login 

Cmd -> `sudo adduser –force-badname AltSchoolUser` 

![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/03419c1e-12d0-40d7-9fe6-f34030579f81)
 

Force the user to change password upon login 

Assumption: User already created as `AltSchoolUser` 

Cmd -> `sudo chage –d 0 AltSchoolUser` 

![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/01b5c1f7-a029-46e2-b5e5-b831fe4e6356)


 

Step 13: Lock a user’s password 

Assumption: A new account name called `testAccount` with a password is created 

User is logged in as a local user of that account 

Cmd -> `passwd –l testAccount` 


![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/78a1da8e-9f51-4843-a4f1-e9f5af4d96f6)

                 

 

Step 14: Create a user with no login shell 

Assumption: User is in the `testAccount` space 

Cmd -> `sudo useradd –s /bin/false AltSchoolUserWithNoShell` 

	 
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/1d04b1d7-7d41-45ec-ab41-b6a391d4d312)

 

Step 15: Disable password-based authentication for ssh 

Assumption: User account name is `AltSchoolUser` and a member of sudo group 

Cmd -> `vi /etc/ssh/sshd_config` 

Run `sudo systemctl restart ssh` after the upper command is run 

Comment the line that starts with `PasswordAuthentication` 

	 
![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/adae8849-5ac0-4e2f-8d23-8649b1697aa7)

 

Step 16: Disable root login for ssh 

Cmd -> `vi /etc/ssh/sshd_config`

Run `sudo systemctl restart ssh` after the upper command is run 

![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/70dd4c0b-ff42-48ca-996b-7963d588c115)

