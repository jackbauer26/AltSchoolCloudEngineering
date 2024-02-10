Step 1: Change into the home directory 

	Cmd -> **cd /home** 

	 
	![image](https://github.com/jackbauer26/AltSchoolCloudEngineering/assets/64382195/dd643ea1-e9fb-4439-8790-ae58049bf23c)

 

Step 2: Create the altschool folder 

	Cmd -> sudo mkdir altschool 

	 

 

Step 3: Create other sub-directories 

Cmd -> sudo mkdir code test personal misc 

	 

 

Step 4: Change to the test sub-directory via the absolute path 

	Cmd -> cd /home/test 

	 

Step 5: change into the test sub-directory via the relative path 

Cmd -> cd  ./test 

              	 

 

Step 6: create a file called fileA with some content 

	Cmd -> echo “Hello A” > fileA 

	 

 

Step 7: Create an empty file in the misc directory and populate it with dummy content 

	Cmd -> echo “Thisis the content of file B” > fileB 

	 

 

Step 8: Copy the contents of fileA into fileC 

Assumption: I am in the personal directory 

	Cmd -> cp ../test/fileA ../testfileC 

	 

 

Step 9: Move contents of fileB into fileD 

	Cmd -> cd ./misc && mv fileB fileD 

	 

 

Step 10: Create a tar archive called misc.tar 

	Cmd: tar –cf misc.tar misc 

	 

 

Step 11: Compress the tar file in step 10 above 

	Cmd: tar –czf misc.tar.gz misc 

                  

 

Step 12: Create a user and force the user to change their password upon login 

Cmd -> sudo adduser –force-badname AltSchoolUser 

 

Force the user to change password upon login 

Assumption: User already created as AltSchoolUser 

Cmd -> sudo chage –d 0 AltSchoolUser 

 

 

Step 13: Lock a user’s password 

	Assumption: A new account name called testAccount with a password is created 

	User is logged in as a local user of that account 

Cmd -> passwd –l testAccount 

                 

 

Step 14: Create a user with no login shell 

	Assumption: User is in the testAccount space 

	Cmd -> sudo useradd –s /bin/false AltSchoolUserWithNoShell 

	 

 

Step 15: Disable password-based authentication for ssh 

	Assumption: User account name is AltSchoolUser and a member of sudo group 

	Cmd -> vi /etc/ssh/sshd_config 

		Run sudo systemctl restart ssh after the upper command is run 

		Comment the line that starts with PasswordAuthentication 

	 

 

Step 16: Disable root login for ssh 

	Cmd -> **vi /etc/ssh/sshd_config** 

		Run sudo systemctl restart ssh after the upper command is run 

	 
