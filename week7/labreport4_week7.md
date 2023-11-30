# Cloning HTTPS

### Step4
<img width="818" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/8e23abd3-6777-4637-b0ff-e20f2d5ce6fe"> 

I typed: `ssh<spacebar>cs15lfa23ko@ieng6.ucsd.edu` \
This command makes my computer log in to the remote ieng6 account on the desktop of CSE Basement. The result went successfully without asking for my password. 


### Step5 
<img width="583" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/94c6dff8-2926-4618-a18e-1fa5e2a9ff40"> <br>
I typed: `git<spacebar>clone<spacebar>https://github.com/ucsd-cse15l-s23/lab7<Enter>` <br>
I cloned my fork of the repository from my Github account. This command cloned the repository to ieng6 and named the folder "lab7".

### Step6
<img width="609" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/38b31a86-ccf2-4734-b431-2be092fe8760"> <br>
I typed: `cd<spacebar>lab7<Enter>` <br>
This command will change my working directory to lab7 folder so I can access the test file and run it. <br>
Then I typed: `bash<spacebar>test.sh<Enter>` <br>
This command runs the bash script which runs the test on the .java file in the lab7 folder. The result shows that we obtained 1 failure. <br>

### Step7
<img width="400" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/88b2cfa6-d651-476c-b225-dc7e9e3b2c0b"> <br>
I typed: `vim<spacebar>ListExamples.java<Enter>` <br>
This command uses vim to open ListExamples.java so I can edit the text in the file to fix the failure. <br>

<img width="709" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/be3ad545-68d0-4b83-b302-3ea1a84acb81"> <br>
This displays the ListExample.java in vim mode after I clicked <Enter\>  <br>
To fix the problem, I typed:
43 times `j`, 12 times `l`, `i<backspace>2<esc>:wq!<Enter>` <br>
By typing 43 times `j`, I moved my cursor from the first line of the file to the line where the code needed to be fixed. Then by typing 12 times `l`, I moved my cursor right next to `1` from `index1` in the line in the java file. Typing `i` then allows me to enter insert mode. I used `<backspace>` to delete the `1` so the line of code changes from `index1 += 1` to `index += 1`. Then by typing `2`, I update the line of code from `index += 1` to `index2 += 1`. <br>
<img width="1141" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/66720230-8e6e-4d8c-89aa-160536259b5e"> <br>

This fixes the failure so I exit the insert mode by pressing `<esc>`. Then in the standard mode of vim, I typed `:wq!<Enter\>`  which helps me save and exit the vim mode. <br>
Now I'm back to my terminal. <br>
<img width="449" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/41b143cf-ef19-40ce-a00a-af3e62c87e6b">   <br>

### Step8
<img width="431" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/f3b4064f-315b-4258-b343-d7e2f04d28d5">  <br>
I typed: `bash<spacebar>test.sh<Enter>` <br>
This command runs the bash script called test.sh in the working directory, and test.sh runs the JUnit test. After changing the code by using vim, the test runs successfully by showing "OK (2 tests)" as a result of the command. <br>

### Step9
I typed: `git<spacebar>add<spacebar>ListExamples.java<Enter>` <br>
This command adds the change I just made using vim in the working directory to the staging area. <br>

I typed: `git<spacebar>commit<Enter>` <br>
This command leads to the vim mode where I need to add a commit message on the change I just made. 
<img width="1129" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/1463491f-1d8a-437a-b7e2-1ea892458c56"> <br>

I typed: `i#<spacebar>incrementation in the second loop changed from index1 to index2<esc>:wq!` <br>

<img width="726" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/54102f98-e432-4567-ba38-92bbbd53b058"> <br>
 

Coming back to the terminal, I added the commit message "incrementation in the second loop changed from index1 to index2" successfully. <br>
Then I typed: `git<spacebar>push`  <br>

<img width="1097" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/b48cdc30-0593-4c34-9bda-b3ef7ae1f56d"> <br>

The picture shows that because I cloned a https URL, the `git push` command will not work. So the pushing is unsuccessful. <br>
<br>
<br>




# Cloning SSH 
### Step4
<img width="796" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/311da534-119c-4d45-9306-70fff861acc5"> <br>
I typed: `ssh<spacebar>cs15lfa23ko@ieng6.ucsd.edu` <br>
This command makes my computer log in to the remote ieng6 account on the desktop of CSE Basement. The result went successfully without asking for my password. 

### Step5
<img width="577" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/816c935e-f874-476a-a180-50015b6bfd99"> <br>
I typed: `git<spacebar`>clone<spacebar>git@github.com:cgxxcg/lab7.git<Enter>` <br>
This command clones the repository using ssh url and it creates a folder named "lab7-2" in my working directory. By cloning using ssh url, I'm able to push the change to github. <br>
This works because I created the SSH key which can be used to authenticate to GitHub.

### Step6
<img width="615" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/0d50c81a-3c6a-418a-948c-fd228e2e3ca3"> <br>
I typed: `cd<spacebar>lab7-2<Enter>` <br>
This command will change my working directory to lab7 folder so I can have access to the test file and run it. <br>
Then I typed: `bash<spacebar>test.sh<Enter>` <br>
This command runs the bash script which runs the test on the .java file in the lab7 folder. The result shows that we obtained 1 failure. <br>

### Step7
<img width="428" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/b3e8eed8-e2e2-4ec8-b88d-63f5d176bea9"> <br>
I typed: `vim<spacebar>ListExamples.java<Enter>` <br>
This command uses vim to open ListExamples.java so I can edit the text in the file to fix the failure. <br>
Then I enter the vim standard mode of ListExamples.java: <br>
<img width="728" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/026c08a0-c02b-4934-a2fb-0eeef663278f"> <br>
To edit the file and fix the code, I need to enter insert mode and move my cursor to the desired place. <br>
To achieve this, I typed: `lli<backspace>2<esc>:wq!<Enter>` <br>
These commands help move my cursor to the right two characters so it is right behind `index1`. Then by using backspace and typing 2, I changed `index1` to `index2`. After fixing the code, pressing <esc> helps me exit insert mode and get back to standard mode so that I can use the terminal command in vim to save the change and exit vim. This is done by typing `:wq!`. <br>
<img width="1141" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/66720230-8e6e-4d8c-89aa-160536259b5e"> <br>
After typing the above commands, I come back to my terminal. 

### Step8
<img width="469" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/132d9b2c-1359-4e21-9a7b-2344eff6bf6b"> <br>
I typed: `bash<spacebar>test.sh<Enter>` <br>
This command runs the bash script called test.sh in the working directory, and test.sh runs the JUnit test. After changing the code by using vim, the test runs successfully by showing "OK (2 tests)" as a result of the command. <br>

### Step9
I typed: `git<spacebar>add<spacebar>ListExamples.java<Enter>` <br>
<img width="480" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/ea25db04-0148-47b1-8bc1-2bc8cc3f0232"> <br>
This command adds the change I just made using vim in the working directory to the staging area. Nothing is printed in the terminal. <br>
I typed: `git<spacebar>commit<Enter>` <br>
<img width="482" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/4db4032f-0d94-44dc-b2d1-7f3a65fd9b0a"> <br>
This command leads to the vim mode where I need to add a commit message on the change I just made. 
<img width="704" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/8958b17f-1e38-43ff-bb98-88ffb04a7cf9"> <br>
I typed: `i#<spacebar/>incrementation in the second loop changed from index1 to index2<esc>:wq!` <br>
By typing `i`, I entered insert mode so I could type my commit message. Then I typed my commit message and by pressing `<esc>`, I exit the insert mode coming back to standard mode. Then I typed `:wq!`. This saves my change in the file and exits vim. 
<img width="755" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/20ba79fe-fac0-4476-a370-d1a7968ff6fa"> <br>

Coming back to the terminal, I successfully added the commit message "incrementation in the second loop changed from index1 to index2" successfully. <br>
Then I typed: `git<spacebar>push`  <br>
<img width="776" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/6d63f6c8-ff37-4e31-b2ef-b546f865ad38"> <br>
To update the change I made and make it shown on GitHub, I need to push the change. This is done by using the `git push` command.
The picture shows that `Everything up-to-date`, which tells me the pushing is successful. <br>
<br>
<br>
