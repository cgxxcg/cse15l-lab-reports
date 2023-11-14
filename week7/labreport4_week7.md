# Cloning HTTPS

### Step4
<img width="818" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/8e23abd3-6777-4637-b0ff-e20f2d5ce6fe"> 

I typed: ssh<spacebar\>cs15lfa23ko@ieng6.ucsd.edu \
This command makes my computer log in to the remote ieng6 account on the desktop of CSE Basement. The result went successfully without asking for my password. 


### Step5 
<img width="583" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/94c6dff8-2926-4618-a18e-1fa5e2a9ff40"> 
I typed: git<spacebar\>clone<spacebar\>https://github.com/ucsd-cse15l-s23/lab7 <Enter\> \
I cloned my fork of the repository from my Github account. This command cloned the repository to ieng6 and named the folder "lab7".

### Step6
<img width="609" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/38b31a86-ccf2-4734-b431-2be092fe8760"> 
I typed: cd<spacebar\>lab7<Enter\> \
This command will change my working directory to lab7 folder so I can access the test file and run it. \
Then I typed: bash<spacebar\>test.sh<Enter\> 
This command runs the bash script which runs the test on the .java file in the lab7 folder. The result shows that we obtained 1 failure. 

### Step7
<img width="400" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/88b2cfa6-d651-476c-b225-dc7e9e3b2c0b"> 
I typed: vim<spacebar\>ListExamples.java<Enter\>
This command uses vim to open ListExamples.java so I can edit the text in the file to fix the failure. \

<img width="709" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/be3ad545-68d0-4b83-b302-3ea1a84acb81"> 
This displays the ListExample.java in vim mode after I clicked <Enter\>  \
To fix the problem, I typed: \
43 times j, 12 times l, i, <backspace\>, 2, <esc\>, :wq!<Enter\> \
By typing 43 times j, I moved my cursor from the first line of the file to the line where the code needed to be fixed. Then by typing 12 times l, I moved my cursor right next to "1" from "index1" in the line in the java file. \
Typing "i" then allows me to enter insert mode. I used <backspace\> to delete the "1" so the line of code changes from "index1 += 1" to "index += 1". Then by typing 2, I update the line of code from "index += 1" to "index2 += 1".
This fixes the failure so I exit the insert mode by pressing <esc\>. Then in the standard mode of vim, I typed \\\ :wq!<Enter\> \\\which helps me save and exit the vim mode. \
Now I'm back to my terminal. \
<img width="449" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/41b143cf-ef19-40ce-a00a-af3e62c87e6b">   

### Step8
<img width="431" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/f3b4064f-315b-4258-b343-d7e2f04d28d5">  
I typed: bash<spacebar\>test.sh<Enter\>
This command runs the bash script called test.sh in the working directory, and test.sh runs the junit test. After changing the code by using vim, the test runs successfully by showing "OK (2 tests)" as a result in the command.

### Step9
I typed: git<spacebar\>add<spacebar\>ListExamples.java<Enter\>
This command adds the change I just made using vim in the working directory to the staging area.

I typed: git<spacebar\>commit<Enter\>
This command leads to the vim mode where I need to add a commit message on the change I just made. 

<img width="1129" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/1463491f-1d8a-437a-b7e2-1ea892458c56"> 

I typed: i#<spacebar/>incrementation in the second loop changed from index1 to index2<esc>:wq! 

<img width="726" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/54102f98-e432-4567-ba38-92bbbd53b058">
 

Coming back to the terminal, I added the commit message successfully. \
Then I typed: git<spacebar\>push 

<img width="1097" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/b48cdc30-0593-4c34-9bda-b3ef7ae1f56d"> 

The picture shows that because I cloned a https url, the "git push" command will not work. So the pushing is unsuccessful.





## Cloning SSH 
### Step4
<img width="796" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/311da534-119c-4d45-9306-70fff861acc5"> 
I typed: ssh<spacebar\>cs15lfa23ko@ieng6.ucsd.edu \
This command makes my computer log in to the remote ieng6 account on the desktop of CSE Basement. The result went successfully without asking for my password. 

### Step5
<img width="577" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/816c935e-f874-476a-a180-50015b6bfd99"> 
I typed:git<spacebar\>clone<spacebar\>git@github.com:cgxxcg/lab7.git<Enter> \
This command clone the repository using ssh url and it create a folder named "lab7-2" in my working directory. By cloning using ssh url, I'm able to push the change to github. \
This works becasue I created the SSH key which can be used to authenticate to GitHub.

### Step6
<img width="615" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/0d50c81a-3c6a-418a-948c-fd228e2e3ca3"> 
I typed: cd<spacebar\>lab7-2<Enter\> \
This command will change my working directory to lab7 folder so I can have access to the test file and run it. \
Then I typed: bash<spacebar\>test.sh<Enter\> 
This command runs the bash script which runs the test on the .java file in the lab7 folder. The result shows that we obtained 1 failure. 


