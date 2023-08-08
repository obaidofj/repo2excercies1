# Git Kata: Basic Staging

This kata will examine the staging area of git.

In git we are working with three different areas:

* The working directory where you are making your changes
* The staging area where all changes you have added through `git add` will stay
* The repository where every commit ends up, making your history. To put your staged changes in here you issue the `git commit` command.

A file can have changes both in the working directory and staging area at the same time.
These changes do not have to be the same.

We will also work with `git restore` to restore the staged changes of a file, and `git checkout` to return a file to a previous state.

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You live in your own repository. There is a file called `file.txt`.

1. What's the content of `file.txt`?
    its content is just:1

2. Overwrite the content in `file.txt`: `echo 2 > file.txt` to change the state of your file in the working directory (or `sc file.txt '2'` in PowerShell)
    done

3. What does `git diff` tell you?
    Tells me that the first version and second version of file.txt are diferent

4. What does `git diff --staged` tell you? why is this blank?
    Tells me that there is no difference between any files in the staging area
    and it is blank becuase we did not add the changed files to the staging area.

5. Run `git add file.txt` to stage your changes from the working directory.
    done

6. What does `git diff` tell you?
7. What does `git diff --staged` tell you?
8. Overwrite the content in `file.txt`: `echo 3 > file.txt` to change the state of your file in the working directory (or `sc file.txt '3'` in PowerShell).
9. What does `git diff` tell you?
    Tells me no changes in the working directory in files that are not added

10. What does `git diff --staged` tell you?
    Tells me that there is difference between first version and second version of the file that added to the staging area

11. Explain what is happening
    we made change to the file.txt in the staging area then it is marked as there is diff between first state and second state
    of the file , then we add it to the staging area . so we can commit the changes now.

12. Run `git status` and observe that `file.txt` are present twice in the output.
    done

13. Run `git restore --staged file.txt` to unstage the change
    done

14. What does `git status` tell you now?
    Tells me that it is now modified
    
15. Stage the change and make a commit
16. What does the log look like?
17. Overwrite the content in `file.txt`: `echo 4 > file.txt` (or `sc file.txt '4'` in PowerShell)
18. What is the content of `file.txt`?
19. What does `git status` tell us?
20. Run `git restore file.txt`
21. What is the content of `file.txt`?
22. What does `git status` tell us?

## Useful commands

- `git add`
- `git commit`
- `git commit -m "My lazy short commit message"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `git restore --staged`

## Aliases

You can set up aliases as such:
`git config --global alias.lol 'log --oneline --graph --all'`
This might be useful to you.
