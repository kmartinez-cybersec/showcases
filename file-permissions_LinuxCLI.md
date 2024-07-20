<h1>Changing File Permissions in Linux</h1>
<h2>Description</h2>

The research team at this organization needs to check and update file permissions for files and subdirectories within the `../projects` directory. To update permissions correctly, the following tasks are completed:

<h2>Walkthrough</h2>
<h3>Check file and directory details</h3>
To check permissions of files within the  `../projects` directory, I first navigate to the subdirectory using `cd projects`. Afterwards, `ls -l` is used to list the file and directory permissions. The output of this is as follows:

```console
total 20
drwx--x--- 2 researcher2 research_team 4096 Oct 14 18:40 drafts
-rw-rw-rw- 1 researcher2 research_team  46 Oct 14 18:40 project_k.txt
-rw-r----- 1 researcher2 research_team  46 Oct 14 18:40 project_m.txt
-rw-rw-r-- 1 researcher2 research_team  46 Oct 14 18:40 project_r.txt
-rw-rw-r-- 1 researcher2 research_team  46 Oct 14 18:40 project_t.txt
```

<h3>Describe the permissions string</h3>

The permissions string for `project_k.txt` is `-rw-rw-rw-`. This indicates that `project_k.txt` is a file and the user, group, and other all have read and write permissions with none having execute permissions. 

<h3>Change file permissions</h3>

The organization does not allow other to have write permissions. To change the permissions on `project_k.txt` so that other does not have write permissions, the command `chmod o-w project_k.txt` is used

<h3>Change permissions on a hidden file</h3>

To list all files, including hidden files, the command `ls -la` is used. The shortened output is as follows:

```console
-rw--w---- 1 researcher2 research_team   46 Feb 18 21:22 .project_x.txt
```

The research team has archived the file `.project_x.txt`, making it a hidden file. It should not have write permissions for anyone, but the user and group should have read permissions. Currently, both the user and group have write permissions and the group is missing read permissions. In order to fix this, the command `chmod u=r,g=r .project_x.txt` is used.

<h3>Change directory permissions</h3>

There is a directory in `../projects` called `drafts`. Only the user, `researcher2` should be allowed to access the drafts directory and its contents. Currently, the permissions for this directory look like:

```console
drwx--x--- 2 researcher2 research_team 4096 Oct 14 18:40 drafts
```

It seems the group mistakenly has execute permissions. To fix this, the command `chmod g-x drafts` is run, removing execute permissions from the group.

<h2>Summary</h2>

To check that all necessary changes have been made, the `ls -la` command is used, the following being the output:

```console
drwxr-xr-x 3 researcher2 research_team 4096 Feb 18 21:22 .
drwxr-xr-x 3 researcher2 research_team 4096 Feb 18 21:53 ..
-r--r----- 1 researcher2 research_team   46 Feb 18 21:22 .project_x.txt
drwx------ 2 researcher2 research_team 4096 Feb 18 21:22 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Feb 18 21:22 project_k.txt
-rw------- 1 researcher2 research_team   46 Feb 18 21:22 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 18 21:22 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Feb 18 21:22 project_t.txt
```

All files and subdirectories within the `../projects` directory are confirmed to have the correct permissions. The `ls -la` and `chmod` commands were integral to the process of updating permissions for this organization. The `ls -la` command is first used to check permissions, and the `chmod` command is used to make all necessary changes to permissions.
