# User Guide
Duke is a text-based app for people to manage their recent tasks. It works like a memory keeper to record users' deadlines, events, todos and their completion statuses.
***
## Quick start
1. Ensure you have Java `11` installed in your computer.
2. Download the latest `duke.jar` from [here](https://github.com/LilyDaytoy/ip/releases/tag/A-Jar).
3. Copy the file to the folder you want to use as your *home folder* for Duke.
4. Open your Command Line Terminal in the folder where `duke.jar` is located and run Duke using `java -jar duke.jar`.
5. Type the command in the Terminal and press Enter to execute it. For example, type `list` and press Enter will show you all the current tasks you have and their corresponding completion statuses.
   Here are some example commands you can try:
    * `list` List all the current tasks and their completion statuses
    * `find book` Find the tasks including the keyword "book"
    * `done 2` Mark the second task as done
    * `todo quiz` Add the quiz task as a todo task
    * `bye` Exit the app and Duke will save your records automatically for you
6. Look at the **Features** below to get more details about each command.
***
## Features
### Notes
#### Notes about command format:
* Words in `UPPER_CASE` are the parameters to be supplied by the user. e.g. the `TASK_INDEX` in `done TASK_INDEX` is a parameter that user should provide, such as `done 1`.
* If a parameter is expected only once in the command, but you specified it multiple times, only the last occurrence of the parameter will be taken. e.g. if you specified `/by 5pm /by 9pm` then it will be recognized as `/by "5pm /by 9pm"` and display the result as `(by:5pm /by 9pm)`.
#### Notes about the Tasks in Duke:
* There are 3 types of tasks in Duke: `todo`, `deadline`, `event`.
  * These three types are distinguished by how user inputs the `TIME` parameter.
  * `TIME` parameter in Duke will only be recognized as a string with no actual time meaning, any format of time you want to record will be ok.
* Here are what the 3 types of Tasks represent:
  * `todo`: a task you need to do with no `TIME` parameter specified.
  * `deadline`: a task you need to complete before the deadline, which is the `TIME` parameter you provide.
  * `event`: a task you need to do during a specific time, which is the `TIME` parameter given by the user.
* The 3 types of tasks are stored in Duke as examples below:
  * `todo`: `[T][] myTodo`
  * `deadline`: `[D][] myDeadline (by : deadline time)`
  * `event`: `[E][] myEveny (at: event time)`
___
### Adding a todo task `todo`
Add a task you need to do with no time specified to the TaskList in Duke.

Format: `todo TASK`

Example:
* `todo watch the lecture`--->`[T][] watch the lecture`
* `todo do the assignment`--->`[T][] do the assignment`
___

### Adding a deadline task `deadline`
Add a deadline task you need to complete before a certain time to the TaskList in Duke.

Format: `deadline TASK /by TIME`

Example: 
* `deadline complete the quiz /by Firday`--->`[D][] complete the quiz (by: Friday)`
* `deadline submit the project /by Monday 12pm`--->`[D][] submit the project (by: Monday 12pm)`
___
### Adding an event task `event`
Add an event task you need to do during a certain time to the TaskList in Duke.

Format: `event TASK /at TIME`

Example:
* `event group meeting /at Monday 6pm`--->`[E][] group meeting (at: Monday 6pm)`
* `event meet with prof Li /at Tuesday 1pm`--->`[E][] meet with prof Li (at: Tuesday 1pm)`
___
### List all the tasks `list`
List all the tasks in the TaskList in Duke and show their completion statuses.

Format: `list`

![list screenshot](https://i.postimg.cc/Y9PYmcPW/2021-09-29-5-20-42.png)
___
### Search for a task `find`
Display all the tasks containing a specific keyword.

Format `find KEYWORD`

Example:
* `find book` will return `read book`,`book a meeting room`
* `find work` will return `do homework`,`work woth my groupmates`
___
### Mark a task as done `done`
Mark a task in the TaskList in Duke as done, change the symbol from `[ ]` to `[x]`

Format: `done TASK_INDEX`
* The TASK_INDEX refers to the index displayed in the TaskList.
* The TASK_INDEX must be in a valid range present in the TaskList.
Example:
* `done 1` marks the first task in the TaskList as done. e.g. the first task `[T][] read book` will change to `[T][x] read book`
___
### Deleting a task `delete`
Remove a task from the TaskList, and it will not be displayed in the list anymore

Format: `delete TASK_INDEX`
* The TASK_INDEX refers to the index displayed in the TaskList.
* The TASK_INDEX must be in a valid range present in the TaskList.

Example:
* `delete 1` deletes the first task in the TaskList. e.g. the first task `[T][] read book` will no longer be in the list anymore.
___
### Exit `bye`
Exit form Duke app
Format: `bye`
___
### Saving the data
Duke will automatically save the data for you in hard disk every time you input a command in order to reload your previous tasks next time when you use it.
___
### Editing your data file
Users can edit the file `data.txt` and `inputFile.txt` to change their TaskList, but note that only the valid change in the correct format can work, otherwise Duke will not run.
***
## Command Summary
Operation | Format and Example
--------- | -----------
Add todo | `todo TASK`  e.g. `todo read book`
Add deadline| `deadline TASK /by TIME` e.g. `deadline complete quiz /by Friday`
Add event | `event TASK /at TIME` e.g. `event meeting /at Monday`
List tasks |  `list`
Search tasks | `find KEYWORD` e.g. `find book` `find work`
Delete a task | `delete TASK_INDEX` e.g. `delete 1`
Mark a task as done | `done TASK_INDEX` e.g. `done 1`
Exit | `bye`
***

## Reference
The template of the User Guide is followed by [AddressBook Level 3 (AB3) User Guide](https://se-education.org/addressbook-level3/UserGuide.html#editing-a-person--edit).