## Lab #4
*May 22, 2023*

> Part 1: Reproducing Tasks

For this lab report, I am reproducing the tasks from Week 7's lab activities. Below will
contain a screenshot of every step and the keys I used to complete the tasks.

## Step 4: Log Into ieng6

![Step 4](step4_lab4.png)
Keys Used: `ssh cs15lsp23pf@ieng6.ucsd.edu <enter> tv9z$EE9pdfBd.. <enter>` 
Because I was using a fresh terminal I had to manually enter my username and password in order to login.

## Step 5: Clone the fork of the repository

![Step 5](step5_lab4.png)
Keys Used: `Ctrl-C Ctrl-V <enter>`
I copied the command `git clone https://github.com/ucsd-cse15l-s23/lab7` from the lab write up and pasted it into my terminal.

## Step 6: Run the Tests (They will fail)

![Step 6](step6_lab4.png)
Keys Used: `<up> <up> <enter> <up> <up> <enter>`
The commands to compile and run ListExamples/ListExamplesTests, and the junit tests were already in my search history (2 lines up), so I used the up arrows
to access it.

## Step 7: Correct ListExamples.java

![Step 7](step7_lab4.png)
Keys Used: `vim ListExamples.java <enter> kllllllllllxi2 <esc> :wq`
I used the `vim` command to open ListExamples.java, and the had to go up one line, right 10 characters to reach the character I needed to change.
I then used `x` to remove the 1 and then `i 2` to insert 2. I then went back to normal mode using `esc` and used `:wq` to save and quit vim.

## Step 8: Run the Tests (They will pass)

![Step 8](step8_lab4.png)
Keys Used: Keys Used: `<up> <up> <enter> <up> <up> <up> <enter>`
Since I had recently used the compile/run commands, I used the arrow keys to access them from my search history, with the compile command being in the second line and
the run command being in the third line.

## Step 9: Commit and Push the Changes.

![Step 9](step9_lab4.png)
Keys Used: `git add . <enter> git commit -m "Updated! <enter> git push`
My `git push` was not working, and said that I did not have permission to push my changes. I assume I'm attempting to push to the original repository rather than my clone, but I'm not sure how to fix it.
I posted my issue on EdStem, and if I gets answered before the due date for this lab, then I will return and update this step with the reason why it wasn't working.
