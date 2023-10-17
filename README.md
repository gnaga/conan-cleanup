## Clean up of Conan artifactory remote repository
***Note:* Instead of Deleting artifact, this script will move to backup repository**

Below script will perform 
1. Find the conan packages that are not used in last 90 days
2. Move them to another repo (provided by the user).
3. After a few days/weeks the files moved to bkp repo can be deleted.

### Pre-requisites 
1. Install JF CLI and jq
2. configure JF CLI to jfrog artifactory and make this as default

### Scripts Arguments  
1. Source repository 
2. Target repository or backup repository

### How to run 
```
bash conancleanup_mv.sh myconan myconanbkp
```
### check if all packages are removed.
```
conan search "zug/0.1.0@" -r myconan

Output
------
Existing packages for recipe zug/0.1.0:

Existing recipe in remote 'myconan':

There are no packages for reference 'zug/0.1.0', but package recipe found.

```
