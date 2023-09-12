I created a bash script for handling


`git add.`, `git commit -m ""` and `git push`


Don't ask why,
Yes, I will tell
For a developer, these 3 commands are the most important to work on on a daily basis.


But it's a little bit time-consuming—not much, but 2 seconds, I can say.


So I created this script.
Follow me.


1. Create a file
```bash
vim gitpush.sh
```
2. The **Code**
```shell
#!/bin/bash
git add.
git commit -m "$1"
git push
```
<details>
<summary>If you want to understand each line</summary>


</details>
3. Exit **the vim**
a. Enter `Esc`
b. Enter `:`
c: Enter `wq`
! [exit vim] (https://imgur.com/XA9IOdC.png)


The entire file should be like this:
![](https://imgur.com/PglpMBb.png)


Now we need to give execute permission to the file.
Follow the command.
```bash
chmod 700 gitpush.sh
```
<details>
<summary>Command breakdown</summary>
chmod: This is used to change the file permissions.
700: 700 is divided into 3 groups: a) 7, b) 0, and c) 0.


**a** refers to the current user.
**b** refers to the group
**c** refers to other users in the system.


Group **a** is 7, which means the current user has all the permissions. You can understand this by
[
4: read
2: write
1: execute
]


So, 7 = 4 + 2 + 1, so the current user will have all the permissions.
0 means no permissions.
</details>


The entry steps will look like:
![](https://imgur.com/CbtNfLo.png)


The gameplay:
![gameplay](https://imgur.com/9Jj7Hhk.png)
As you can see, I have used the absolute path of the file with just the commit message. Liek simple.


But, 
In bash, we can use alias to avoid typing the file path every time.
Follow me:
1. Go to the Home directory
```shell 
cd ~
````
2. Open your shell script; I'm using zsh.
```bash
vim .zshrc
```
If you are using bash, it must be `.bashrc`. You can check that by
```shell
echo $SHELL
```
3. The core command
```bash
alias -g gitpush='/home/scor32k/blogs/scripts/gitpush.sh $1'
```
restart the shell (close the terminal and open again). This will globally set the alias.


Not the fun
Follow
![final](https://imgur.com/rkkWiJV.png)


I have only used
```shell
git push "commit message"
```
and all three imp git commands are done.


This was just a fun project. I thought of creating
