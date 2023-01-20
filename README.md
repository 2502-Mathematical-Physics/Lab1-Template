# Lab 1

## Navigating with the Command Line

### Terminology
* **Command Line** or **Terminal**: This is where you can type commands to manipulate and get information about your computer
* **Directory**: A folder

### Commands
* `ls` (List) : list all files and directories in the current directory
* `pwd` (Print working directory): Lists the current directory you're in
* `cd [directory]` (Change Directory): Switches the current directory to the one you specify
* `cd ..`: Goes to the parent directory

### Example
If you have the following directory structure:
```
Documents
	Textbooks
		Physics
			2502_course_notes.pdf
			nearing_mathematical_physics.pdf
		Mathematics
```
* `Textbooks` is the parent directory of the `Physics` and `Mathematics` directories
* `Physics` is the parent directory of the `2502_course_notes.pdf` file

```bash
$ cd Documents/Textbooks
$ ls
Physics Mathematics
$ cd Physics
$ pwd
Documents/Textbooks/Physics
$ ls
2502_course_notes.pdf nearing_mathematical_physics.pdf
```

## Git and Github
### Terminology
* **Local**: Stuff that happens on your laptop or desktop computer
* **Remote**: Stuff that is in the cloud or on another server
* **Github**: The remote cloud storage for git (think Google Drive)
* **Git**: A local tool to track changes in code
* **Repository**: 

### Commands
#### Commands for setting up git the first time
* `git config --global user.email "example@example.com"`
* `git config --global user.name "First Last"`

#### Commands for starting a new repository
* `git clone [url]`: Download the repository located at the url

#### Commands to run everytime you push a change
* `git add [filename]`: Tell git to track changes for this file
* `git diff`: Shows the changes you made
* `git status`: Shows modified files
* `git commit -m "message"`: Saves changes to git (local)
* `git push`: Pushes changes remotely (to Github)

### Example (Try This)
Set up git
```bash
$ git config --global user.name "[First Last]"
$ git config --global user.email "[email@example.com]"
$ git config --global credential.helper store
```

Generate a Personal Access Token (Classic) by following the [guide](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).

Make sure the `repo`, `write package`, and `delete package` permissions are checked:
![permissions](https://user-images.githubusercontent.com/122498160/213591159-b88babc2-0091-4c3e-b262-14d34ef12dfd.png)

Open up the terminal on your computer (e.g. Git bash on windows and Terminal on MacOS).

Clone this repository using the following command
```bash
$ git clone https://github.com/2502-Mathematical-Physics/lab1-[username]
Cloning into 'lab1-2502-[username]'...
Username for 'https://github.com': [type username]
Password for 'https://[username]@github.com': [type personal access token here]
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
```

When it asks you for your password, paste your Personal Access Token instead.


If you list the files in your current directory, you'll see that there is a new directory with the name of the repository you cloned
```bash
$ ls
lab1-[username]
```

Then navigate to the directory you just downloaded:
```bash
$ cd lab1-[username]
```

List the files. You will see the pdf of the lab, the README file that you're reading right now, and the mathematica template code:
```bash
$ ls
LabsPHYS2502S23n01.pdf lab1.nb README.md 
```

Let's edit the mathematica template. Open lab1.nb in Mathematica. Then make any change you want (e.g. add the current date).

![Screenshot of adding current date to mathematica notebook](https://user-images.githubusercontent.com/21135985/213498239-63ebd628-de9f-47e3-90bf-6ac31f7a5943.png)

Confirm that the file was modified
```bash
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   lab1.nb

no changes added to commit (use "git add" and/or "git commit -a")

```

Tell git we want to select the `lab1.nb` file 
```bash
git add lab1.nb
```

Save the modification by commiting (only saves change locally):
```bash
$ git commit -m "[Write a descriptive message here about what change you made]"
[main d9af7ae] Add date to lab
 1 file changed, 43 insertions(+), 37 deletions(-)
```

Save the modifications to Github (remote):
```bash
$ git push
```

You can check the github repo to see if the changes were saved remotely. 
![image](https://user-images.githubusercontent.com/21135985/213591507-918b629d-a5c7-47dd-8ef8-2ea75eca4c2b.png)

