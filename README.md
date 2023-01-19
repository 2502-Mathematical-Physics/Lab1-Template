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
Open up the terminal on your computer (e.g. Git bash on windows and Terminal on MacOS).

Clone this repository using the following command
```bash
$ git clone https://github.com/2502-Mathematical-Physics/lab1-[username]
```

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


