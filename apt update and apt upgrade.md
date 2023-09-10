
  
You may have heard or used `sudo apt update` and `sudo apt upgrade`, and you must have thought about what these commands actually do.

So, in this blog, we will learn, what these two commands actually do.

## sudo apt update

When you enter `sudo apt update` in your terminal, this command starts a process that refreshes the package list on the system.

Going in depth (-vv):

1. **Refreshing Packages**: As we know, Linux systems use package managers like APT, which stands for Advanced Package Tool, to manage software packages.  
These package managers maintain a list of available packages and their versions. So, when you run `sudo apt update`, the system contacts the package repositories specified in your software sources (usually found in `/etc/apt/sources.list` or `/etc/apt/sources.list.d/`) and checks for updates.  

	![](https://imgur.com/rx4ez9N.png)

2. **Checking Updates**: The package manager queries each repo (in my case, only one) and checks if there are any new packages or updates available.  
This check is done by comparing the versions of packages in the repository with those installed on your system (side-by-side comparison).

3. **Updating the Local Cache**: If any updates are found, the package manager downloads the updated package information and stores it in a local cache on the system. This cache will contain metadata about the available packages, such as their names, versions, and dependencies. This will be used when we'sudo apt upgrade`.

**Summary**: An update doesn't actually include any updates; it only refreshes the list of available packages and their versions on the system.

## sudo apt upgrade  
This command is usually performed after `update` because to update the packages, we need to have the new versions of the packages.  

This upgrades the installed packages on the system.

Going in depth (-vv):

1. **Package Selection**: The package manager checks the local cache, which was updated during the previous `sudo apt update` command. It identifies which installed packages have newer versions available in the repositories by comparing the old versions with the newer versions.

2. **Dependency Resolution**: If there are updates available, the package manager checks for any dependencies required by the updated packages. It ensures that the installation or upgrade won't break any existing software by resolving and installing any necessary dependencies.

3. **Upgrading Packages**: Once the package manager has determined which packages to upgrade and resolved any dependencies, it begins the upgrade process. It downloads the updated packages from the repositories and replaces the older versions installed on the system with the new ones.

4. **Configuration Updates**: In some cases, when upgrading a package, you might be prompted to review and approve changes to configuration files. The package manager provides options to keep your current configuration, use the new one, or review the differences.

5. **Completion**: After upgrading the selected packages, the package manager provides a summary of the changes, including the number of packages upgraded and any held back due to conflicts or other issues.

**Summary**:  `sudo apt upgrade` upgrades the packages by installing the new verison of the packages.

---


If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
