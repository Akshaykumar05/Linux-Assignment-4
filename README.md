# Linux-Assignment-4
* In this repo I'm documenting 25 Linux Questions as a part of Keenable internship. Let's start the adventure with terminal..
  
**Ques 1: Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.**

``` 
cd /home
```
```
sudo mkdir MyFiles
```
```
cd MyFiles
```
```
 ls
```

**Output**

![Screenshot from 2024-02-05 12-08-10](https://github.com/Akshaykumar05/Linux-Assignment-4/assets/114390890/d81b9eb3-34c9-45dd-a0a2-18901ab76fff)

**Ques 2: Copy a file named "document.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "Documents" within "MyFiles."**

``` 
cd /home
```
```
sudo touch document.txt
```
```
sudo cp document.txt MyFiles/
```
```
cd MyFiles/
```
```
sudo mkdir -p Document
```
```
sudo mv MyFiles/document.txt MyFiles/Document
```

**output**

![Screenshot from 2024-02-05 12-30-15](https://github.com/Akshaykumar05/Linux-Assignment-4/assets/114390890/5931c331-64d1-42f2-9740-66ecd5e73b12)


**Ques 3 : Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.**

``` 
cd /home/MyFiles/
```
```
sudo touch notes.txt
```
```
sudo rm -rf notes.txt
```



**Output**

![Screenshot from 2024-02-05 12-35-44](https://github.com/Akshaykumar05/Linux-Assignment-4/assets/114390890/eda6ec80-91ad-4537-b603-5468b6db66d8)



**Ques 4 : Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.**

```
sudo cd /home/MyFiles/documents
```
```
sudo ln document.txt hardlink.txt
```
```
sudo ln -s document.txt symlink.txt
```
**Output**

![image](https://github.com/Akshaykumar05/Linux-Assignment-4/assets/114390890/10dfa922-c385-4617-86c1-b135fa09f472)


**Ques 5 : In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.**

```
sudo ls /home/MyFiles/a*.txt
```

**Output**

![image](https://github.com/Akshaykumar05/Linux-Assignment-4/assets/114390890/567c8124-8cc7-4fff-a311-0923892d66c3)



**Ques 6: Rename all files in the "Documents" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.**

```
cd /home/MyFiles
```
```
sudo vim rename.sh
```
```
#!/bin/bash

rename_extension=".bak"

for file in *; do
    if [ -f "$file" ]; then
        rename_file="$file$rename_extension"
        cp "$file" "$rename_file"
        echo "Renamed File $file as $rename_file"
    fi
done
```
```
cd Document
```
```
touch a.txt b c.txt d.txt
```
```
sudo bash ../rename.sh
```
**Output**

![Screenshot from 2024-02-09 18-39-58](https://github.com/Akshaykumar05/Linux-Assignment-4/assets/114390890/838df57e-c420-4ba9-ad8a-09dfad79aedc)


**Ques 7: Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup."**

```
cd /home
```
```
cd MyFiles
```
```
sudo mkdir backup
```
```
cd
```
```
sudo cp /home/MyFiles/Document/* /home/MyFiles/backup/
```

**Output**

![Screenshot from 2024-02-09 18-46-37](https://github.com/Akshaykumar05/Linux-Assignment-4/assets/114390890/8f25734f-3a2d-4c20-a2dc-f93a2f528769)


**Ques 8 :Execute the ls command to list files in the current directory. Save the output to a file named "file_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.**

```
sudo su
```
```
cd /home/MyFiles/
```
```
touch file_list.txt
```
```
cd Document
```
```
chmod +rwx a.txt b
```
```
cd ..
```
```
chmod +rwx file_list.txt
```
```
cd Document
```
```
ls > ../file_list.txt
```
```
grep '\.txt$' file_list.txt
```

**Output**



![Screenshot from 2024-02-02 11-03-35](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/e3837160-18c3-46b0-a58b-954879d260af)

**Ques 9: Create a new text file named "my_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.**
```
cd /home/MyFiles/
```
```
sudo touch my_notes.txt
```
```
sudo vim my_notes.txt
```
**Output**


![Screenshot from 2024-02-02 11-22-48](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/55489b45-3f5d-4b2d-a630-cf437c3fe3d4)

![Screenshot from 2024-02-02 11-26-52](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/ed690270-cf6c-446d-a5a3-9e0bcf7c0b56)

**Ques 10 :Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.**

```
cd /home/MyFiles/
```
```
sudo su
```
```
current_date=$(date)
```
```
echo "current date : $current_date"
```
```
echo "$current_date" >> my_notes.txt
```
**Output**

![Screenshot from 2024-02-02 11-37-48](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/4bf8b699-36ce-4a7b-be32-6654a0858846)

![Screenshot from 2024-02-02 11-42-47](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/c46260f6-236f-4214-b0a5-88cf3fa08e7b)


**Ques 11 : Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.**
```
vim .bashrc
```
```
export CUSTOM_PATH="/home/MyFiles/Document"
```
```
source ~/.bashrc
```
```
echo $CUSTOM_PATH
```
**Output**

![Screenshot from 2024-02-02 14-08-23](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/4e3eb4d2-84aa-4618-9db8-baf1270593f4)

![Screenshot from 2024-02-02 14-09-58](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/35038695-cd2b-4e5e-b76a-7309a1663c88)

**Ques 12 : Use the echo command to add a new line of text to the "my_notes.txt" file without overwriting existing content. Verify that the new text is appended.**

```
cd /home/MyFiles
```
```
sudo su
```
```
echo "I am writing text in new line" >> my_notes.txt
```
```
cat my_notes.txt
```
**Output**

![Screenshot from 2024-02-02 14-21-47](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/66aef82f-825f-4bd8-bb3a-bb924d3f9aaa)

**Ques 13 : List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf_files.txt."**

```
ls /etc | grep 'conf' > conf_files.txt
```
```
vim conf_files.txt
```
**Ques 14 : Open the "my_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes.**

```
cd /home/MyFiles
```
```
sudo vim my_notes.txt
```
**After opening file write below  command after press shift + colon
```
%s/important/critical/g
```
**Output**

![Screenshot from 2024-02-03 10-39-06](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/b519ffe1-db4e-4530-8ac2-45400c9cd356)


**Ques 15 : Create a new user account named "john_doe." Set the user's home directory to "/home/john_doe" and assign the user to the "users" group.**

```
sudo useradd -m -d /home/john_doe -g users john_doe
```
**Output**

![Screenshot from 2024-02-02 15-58-43](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/b207ab3a-bf14-453d-976e-6f927418bd4a)

**Ques 16 : Add the user "john_doe" to the sudoers file, allowing them superuser privileges. Confirm that "john_doe" can execute commands with sudo.**

```
sudo visudo
```
**Inside visudo file write below content and save it and exit**

```
john_doe ALL=(ALL:ALL) ALL
```
**Write any desire path**
```
sudo ls /Desktop
```
```
sudo su
```
**Output**

![Screenshot from 2024-02-02 17-37-03](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/620817c9-3c3d-407b-a145-db82b5d5a44e)

**Ques 17 :Modify the user account "john_doe" to change the default shell to "/bin/bash" and set the account's expiration date to one month from today.**

```
sudo chsh -s /bin/bash john_doe
```
```
sudo chage -E $(date -d "+1 month" +"%Y-%m-%d") john_doe
```
**Output**

![Screenshot from 2024-02-03 11-01-04](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/45bf1950-6121-4c80-bf11-f0e01ce18b6f)


**Ques 18 :Create a new group named "development_team." Add "john_doe" to this group and verify the group's existence.**

```
sudo groupadd development_team
```
```
sudo usermod -aG development_team john_doe
```
```
getent group development_team
```
**Output**

![Screenshot from 2024-02-03 11-04-39](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/1c353beb-db1e-4727-9539-f6240b675779)

**Ques 19 : Remove "john_doe" from the "users" group and add them to the "development_team" group. Confirm the changes.**

```
sudo gpasswd -d john_doe users
```
```
sudo usermod -aG development_team john_doe
```
```
groups john_doe
```
**Output**

![Screenshot from 2024-02-03 11-10-17](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/54848d72-c6dd-4388-9ca3-7b792465358a)

**Ques 20 :Delete the user account "john_doe" and ensure that their home directory is also removed.**

```
sudo userdel -r john_doe
```
```
groups jhon_doe
```
**Output**

![Screenshot from 2024-02-03 11-50-23](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/454afda8-aa0e-4269-9338-b58bdc89b47b)

**Ques 21 : Delete the group "development_team" and ensure that all users previously belonging to the group are appropriately handled.**

```
getent group development_team
```
```
sudo usermod -g users jhon_doe
```
```
sudo groupdel development_team
```
```
getent group development_team
```
**Output**

![Screenshot from 2024-02-03 11-56-05](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/3c86c99f-3682-40f3-8b61-8cedc9cf0694)


**Ques 22 : Implement a password policy that requires users to change their passwords every 90 days. Apply this policy to all existing and new user accounts.**

```
sudo chage -M 90 -m 0 -W 7 -I 30 -E -1 $(cut -d: -f1 /etc/passwd)
```
```
sudo vim /etc/login.defs
```
**Inside this file add max pass day as 90 and min pass day as 0**

```
PASS_MAX_DAYS   90
PASS_MIN_DAYS   0
```
**Output**

![Screenshot from 2024-02-03 12-12-05](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/3644184f-f833-47b8-a2a2-b451e18825c4)


![Screenshot from 2024-02-03 12-12-58](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/356acac8-86e3-4d89-a918-6545a4d1c408)

**Ques 23 : Manually lock the user account "john_doe." Attempt to log in as "john_doe" to confirm that the account is locked. Then, unlock the account.**

```
sudo passwd -l john_doe
```
```
su - john_doe
```
```
sudo passwd -u john_doe
```
**Output**

![Screenshot from 2024-02-03 12-21-10](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/c798c600-9574-46db-8e78-a57aec3e0cfa)

**Ques 24 : Use the id command to display detailed information about the "john_doe" user, including user ID, group ID, and supplementary groups.**

```
id john_doe
```
```
id -u john_doe
id -g john_doe
```
```
id -G john_doe
```
**Output**

![Screenshot from 2024-02-03 12-27-32](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/04f4eb82-1a03-4096-b778-e583a75f97c0)

**Ques 25 : Configure the password aging for the user "john_doe" to enforce a maximum password age of 60 days. Confirm that the changes take effect.**

```
sudo chage -M 60 john_doe
```
```
sudo chage -l john_doe
```
**Output**


![Screenshot from 2024-02-03 12-32-24](https://github.com/MOINUDDIN0786/Linux-Assignment-4/assets/64195957/6536b02f-3083-4eb2-bd27-1fa6703e699d)







































