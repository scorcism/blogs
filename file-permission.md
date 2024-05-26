
## What are file permissions ⁉️

File permissions play a crucial role in ensuring proper privacy and security.

Don't worry, I'll guide you through it step by step .

### How do they work ?

Unlike Windows , Linux❤️‍🔥 files cannot be executed directly. This is because file permissions must allow the execution of a file for it to be executed.

File permissions prevent unauthorized access to sensitive files or directories and also ensure data privacy.

In short, without proper file permissions, file execution, access, and modification cannot occur.

Now, before we move into file permissions description, let's understand the Linux roles .

### User Role

There are three roles or entities in the Linux system: user👤, group👥, and others.

Here is the brief overview👀:

👤**User(u):** The Individual user who owns the file, directory. The user is often the person/guy who creatd the file or directory and becomes the owner of the file. The owner has the most extensive control over the it.

👥**Group(g):** Users in the same group as the file owner will have access to the file. To allow a specific set of users to access the file, you can add them to a group and grant access to that group. This way, only the users in that group will have access to the file. Group permisssions allow collaboration among users with the similar access.

**Others(o):** Everyone else who has access to the system but isn't the owner or in the group associated with the file. Others include the general public.

**All three users/entities will have three types of permissions**

### 💭Entities Permission
📕**Read(r):** Allows viewing the content of a file or listing the content of a directory. Read permission is represented by the "r" symbol. Read permission also has an octal value of 4. Octal value is another way↕️ of representing file permissions.

We will explore this further.

✍️**Write(w):** Allows modification of the file’s content or creating, deleting and renaiming within the directory. Write permission is represented by “w” symbol, it has an octal value of **2.**

**Execute(x):** This enables running the file as a program or traversing a directory. Execute has octal value of **1.**

---
To **summarize**, there are three roles in a Linux system: 👤user, 👥group, and others.

-   The user is the owner of the file or directory,
-   Group consists of users who belong to the same group as the file owner,
-   others refers to the general public.

Each of these users has three individual permissions: 📕Read, ✍️Write, and Execute.

-   Read permission allows the user to only read the file, and it is represented by the octal value of 4.
-   Write permission allows the user to modify the file, and it is represented by the octal value of 2.
-   Execute permission allows the user to execute a file or traverse a directory, and it is represented by the octal value of 1.

---
These permissions are organized in a string of nine characters for each file or diectory.

eg:

`rw-r--r--` ([rw-] represents read and write permission for the owner), ([r--]and read only permission to the group) and ([r--]and read only permission to the others).
![one](https://imgur.com/1z8JKC2.png)

### 🌅Viewing file Permissions

To view the permissions of files and directories, you can use the **`ls`** command with the **`-l`** option🛩️. Here's an example:

```bash
	ls -l
```
The output will display file information, including permissions, ownership, group, size, modification date, and filename.

Here's a breakdown of what a typical **`ls -l`** output looks like:

```bash
-rw-r--r-- 1 scor32k scor32k 43 Sep 19 01:00 myfile_scor32k.txt
```

In this example:

-   **`rw-r--r--`** represents the permissions.
-   **`1`** indicates the number of hard links.
-   **`user`** is the owner of the file.
-   **`group`** is the group associated with the file.
-   **`43`** is the file size.
-   **`Sep 19 01:00`** is the modification date.
-   **`myfile_scor32k.txt`** is the filename.

You may be thinking🤔 but how `-rw-r--r--` permission got attached to the file when we created it,

this is becase of **UMASK**.

### USMAK ?

In simple terms, whenever we create a file or directory in a Linux system, the system assigns default permissions to the file or directory based on Linux itself.

Interesting! more

The **umask** is generally set to `022`. You can check that using `umask` command.

**Notes**: The default permission for a file is `666`, and the default permission for a directory is `777`.

The entire process is as follows:

When a user creates a file, it will have a default permission of `666`. The `022` umask will then be subtracted from `666`, resulting in a final permission of `644`.

The user will have read and write permission(6=4+2), the group will have read permission(4), and others will also have read permission(4).

🌱You can also try this with a directory: `777` - `022` = `755`.

### Modifying file permissions

**chown** which stands for change file mode or change file permission command is used to modify the permissions.

**Add execute permission to file.**

```bash
chmod +x myfile.txt
```
This `+x` adds execute permission to the file.

```bash
-rwxr-xr-x 1 scor32k scor32k 43 Sep 19 01:00 myfile.txt
```

See the image below:
![two](https://imgur.com/idXVxna.png)

### **Remove Permission**

```bash
chmod -x myfile.txt
```

-   `+` is used to add permission.
-   `-` is used to remove permission.

```bash
-rw-r--r-- 1 scor32k scor32k 43 Sep 19 01:00 myfile.txt
```

![https://imgur.com/B70kTi9.png](https://imgur.com/B70kTi9.png)

### **Give permission based on specifc role:**

1.  **User/owner Permission**

**Add Permission**

```bash
chmod u+x myfile.txt
```

![https://imgur.com/NTzgJhH.png](https://imgur.com/NTzgJhH.png)

**Remove Permission**

```bash
chmod u-x myfile.txt
```

![https://imgur.com/Z8r8D7f.png](https://imgur.com/Z8r8D7f.png)

2.  **Group Permisson**

```bash
chmod g+x myfile.txt
```

![https://imgur.com/HwjwJCO.png](https://imgur.com/HwjwJCO.png)

3.  The same goes for **others(o)**. You can experiment with this.

### Octal Mode in chmod

This is the advanced version of file permission manipulation. Here, we use numeric values to represent each permission types (read, write, execute).

-   Read[r] = 4
-   Write(w) = 2
-   Execute(x) = 1

To set permissions using an octal value, we assign a three-digit number to each entity (user, group, others) based on the desired permission.

**Note:** The file or directory can max have 777 file permission, which means the user,group and others will have read, write, and execute permission resepectively.

## Modifying file permissions, Octal edition.

Before moving forward,

we need to remember that the permissions are just a combination of (4, 2, 1), and as per our requirements, we can alter this.

Suppose we want to add read and execute permission to only the user and read permission to groups and others.

So,

We use `1` as the octal value for execute, and for read, we use `4`.

The combined value will be `544`.

### Example 1:

**Add read and execute permission to the user, and read permission to the group and others.**

```bash
chmod 544 myfile.txt
```

![https://imgur.com/H2DPPRF.png](https://imgur.com/H2DPPRF.png)

To be precise devide the `r-xr—r—` into 3 blocks `r-x r-- r--`, this will clear your doubts.

**Note: T**he `-` before permission is for the file type. **`-`** for **file** and **`d`** is for directory.

![https://imgur.com/pAW6nHh.png](https://imgur.com/pAW6nHh.png)

### Example 2:

Suppose, we want to add read and write to user, write and execute to group and read to others.

user: read = 4, write = 2 ⇒ 4+2 ⇒ 6

group: write = 2, execute = 1 ⇒ 2+1 ⇒ 3

others: read = 4 ⇒ 4

```bash
chmod 634 myfile.txt
```

![https://imgur.com/WSSOFIM.png](https://imgur.com/WSSOFIM.png)

If i take examples there will not be any end, you can play around with this.

### Changing file ownership

**chown** which stands for change ownership command is used to chnage the ownership of file or directory.

```bash
chown abhishek myfile.txt
```

-   you my require root privelage.

![https://imgur.com/WQNSSYn.png](https://imgur.com/WQNSSYn.png)

### Changing file group Ownership

**chgrp** command will be used to chnage the file group.

```bash
chgrp geet myfile.txt
```

-   add myfile.txt to group geet

![https://imgur.com/DHHszRl.png](https://imgur.com/DHHszRl.png)

### Some tips

-   **Never use 777 →** It’s a severe security risk and show be avoided.
-   **use ls -l** → This displays detailed information about files and directories, including their permissions.
-   **use chmod**
-   **Limit the global access**
-   **umask matters a lot**
-   **Review permissions regularly**.

---


If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
