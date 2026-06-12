# task-cli
task-cli is a simple tool used to have a lightweight TODO list. Hate electron? Got bored of BIG TECH companies having the 'best' TODO list apps? Have ADHD? This is your tool. It runs at your terminal, uses simple commands (task new/finish/list) and runs on Lua.

## Basic Commands
### task new [string]
To make new tasks; Spaces allowed, no quotes needed.
### task list

To list your current tasks and status your current progress, with a timestamp showing you when you've submitted the task.
### task oops [id] [text]
If you managed to make a typo or just want to repharse your task, you could!

**Tip**: You could use your 'brain' to get the id (first task = id=1, second task...) or just use the list.

### task finish [id]
Finishs a task and saves it for you (for backup/history or for monitoring progress).

### task history
To view previous tasks that you've finished.
### task nuke
To remove all current tasks without backup. Example:
`task nuke`

It overwrites the todo_list file with nothing.

**WARNING**: Someone might say 'Umm where's the confirmation bro 🤓'; the command's name is nuke, it's meant to be used when your list is getting too messy or uncontrollable.
# Installation
Installing task-cli is quite simple. If you want to install it globally, run these commands in your terminal:
```bash
curl -s https://raw.githubusercontent.com/abu-tuqa/task-cli/main/task -o task

chmod +x task

sudo mv task /usr/local/bin/
```
