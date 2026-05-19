# Python and the Raspberry Pi with VS Code (Remote SSH)

In the previous activity, you learned how to connect to your Raspberry Pi over SSH using PuTTY, run basic Bash commands, and use Git and GitHub directly on the Pi.  In this activity, you will move your development workflow into Visual Studio Code on your PC while your code still runs on the Raspberry Pi.

By the end, you will be able to:

- Connect from VS Code on your PC to your Raspberry Pi using the Remote–SSH extension  
- Open folders and files that live on the Pi directly in VS Code  
- Run and modify a Python program on the Pi from within VS Code  

***

## 1. Prerequisites

Before starting, you should already be able to:

- SSH into your Raspberry Pi from Windows using PuTTY  
- Log in with your Pi username and password  
- Run basic Bash commands (`ls`, `cd`, `pwd`, etc.)  
- Use Git on the Pi (clone a repo, commit, push)   

Also required:

- Visual Studio Code installed on your Windows PC  
- Your Raspberry Pi powered on, connected to the same network as your PC  
- SSH enabled on the Raspberry Pi  

If any of these are not true, review the previous “Git, GitHub, and the Raspberry Pi” activity or ask your instructor.

***

## 2. Learn Remote SSH with VS Code

You will follow this tutorial to learn how to program your Raspberry Pi remotely using VS Code:

- **Tutorial link:**  
  [Programming Raspberry Pi Remotely using VS Code (Remote-SSH)](https://randomnerdtutorials.com/raspberry-pi-remote-ssh-vs-code/) [randomnerdtutorials](https://randomnerdtutorials.com/raspberry-pi-remote-ssh-vs-code/)

Work through the tutorial carefully. As you go, make sure you can do ALL of the following on your own:

1. Install the **Remote – SSH** extension in VS Code on your PC. 
2. Add a new SSH host entry for your Raspberry Pi (using `pi@<your-pi-hostname-or-ip>` or your own username).
3. Connect to the Raspberry Pi from VS Code and open a **new VS Code window** that is connected to the Pi. 
4. Open the Pi’s home folder (for example `/home/pi`) in VS Code’s Explorer. 
5. Confirm that the **terminal in VS Code** is actually running on the Pi (not on your Windows machine) by running commands like `pwd` and `uname -a`. 
6. Create a new Python file on the Pi using VS Code, run it from the terminal, and see the output. The tutorial uses an example like `test.py` that prints a message. 

As you follow the tutorial, take quick notes on:

- Any errors you hit and how you fixed them  
- Anything that was confusing the first time through  

You will need those notes later.

***

## 3. Clone this repo on the Raspberry Pi (from VS Code)

Once you can connect to your Pi with VS Code, you are ready to bring Git and GitHub back into the picture.

1. In your **Remote-SSH VS Code window** (the one connected to the Pi), open a terminal.  
2. Navigate to the folder where you want to store your class repos.  Use the `PiProjects` directory you previously made.

3. Clone this repo in that directory.

4. Change into the cloned folder:  

5. In VS Code, use **File → Open Folder…** (in the remote window) and open this folder on the Pi.

You should now see the repo’s files (including `README.md` and `hello_pi.py`) in the VS Code Explorer, and the terminal at the bottom should still be running on the Pi.

***

## 4. Run the starter Python program

This repo includes a starter Python file, `hello_pi.py`. The file might look something like:

```python
print("Hello from your Raspberry Pi!")
```

1. In VS Code (remote window), open `hello_pi.py`.  
2. In the terminal, make sure you are in the repo folder.  
3. Run the program:

```bash
python3 hello_pi.py
```

4. Confirm that you see the output in the terminal.

If this does not work, check:

- Are you in the correct folder (`pwd`)?  
- Does `ls` show `hello_pi.py`?  
- Are you using `python3` instead of `python`?  

***

## 5. Modify `hello_pi.py`

Now you will customize the program and push your changes to GitHub.

1. Edit `hello_pi.py` so that it does **all** of the following:
   - Prints a greeting that includes your name.  
   - Prints the result of a simple calculation (for example, `5 * 7`).  
   - Asks the user to type something (like their favorite food) and then prints a response that includes what they typed.  

   You should end up using:

   - At least **three** `print()` statements  
   - At least **one** variable  
   - At least **one** `input()` call  

2. Save the file in VS Code (`Ctrl+S`).  
3. Run it again from the VS Code terminal and confirm that it behaves as expected.

***

## 6. Commit and push your changes

Just like in the previous Pi activity, you will use Git **on the Pi** to save your work.

In the terminal (still in the repo folder):

1. Check your Git status:

```bash
git status
```

2. Stage your changes:

```bash
git add hello_pi.py
```

3. Commit with a meaningful message:

```bash
git commit -m "Customize hello_pi with input and math"
```

4. Push to GitHub:

```bash
git push
```  

5. Go to the repo on GitHub in your browser and verify that your changes to `hello_pi.py` are visible.

***

## 7. Reflection questions (to turn in or discuss)

Answer these questions in a separate file called `REFLECTION.md` in the repo, or in your engineering notebook (follow your instructor’s directions):

1. Explain in your own words the difference between:
   - SSH into the Pi using PuTTY  
   - Connecting to the Pi using Remote–SSH in VS Code  

2. What are two advantages of using VS Code with Remote–SSH compared to editing files directly in the terminal on the Pi?

3. When you run `python3 hello_pi.py` from the VS Code terminal, where is the code actually executing: on your Windows PC or on the Raspberry Pi? How do you know?

4. Describe one error you encountered while following the Random Nerd Tutorials guide and how you solved it. [randomnerdtutorials](https://randomnerdtutorials.com/raspberry-pi-remote-ssh-vs-code/)

5. If you were going to teach this workflow to a student who only knows how to log in with PuTTY, what are the **three most important steps** you would show them?

***

## 8. Extensions (optional challenges)

If you finish early, try one or more of these:

- Add some basic error handling to your program (for example, what if the user types something unexpected?).  
- Use a `while` loop to let the user run the program multiple times without restarting it.  
- Create a new Python file in the same repo, experiment with a simple menu system, and commit and push those changes as well.  

Ask your instructor before starting any GPIO or hardware-related projects.

***

If you share your students’ grade level and how much Python they already know (if at all), what would you like to add or remove from these instructions to match their level best?
