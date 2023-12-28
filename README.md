# org-mode-voice-in

## Introduction
Org-mode-related voice commands for the browser-based Voice In.
The utilization of these custom commands requires a subscription to Voice In Plus.
Voice In works only in Google Chrome.
It works in any text area, such as in:

- markdown documents in GitHub while in the editing mode
- markdown documents in Jupyter Lab and Jupyter Notebooks
- markdown documents in 750words.com
- tex documents on Overleaf.com
- Gmail
- Outlook webmail
- Might work in a docker-hosted Emacs

Org-mode is an advanced form of Markdown that has strong support for the following activities:

- outlining
- time and project management through the org-agenda package
- Knowledge Management through the that zettelkasten method implemented in org-roam
- academic manuscript preparation with exports to PDF and several alternative packages for inserting citations
- the preparation of blog posts the export to HTML
- book preparation leveraging the features of LaTeX
- the preparation of reveal style slides in HTML with org-real
- tables that enable computations to be run automatically on a by-row or by-column basis

All the features of org-mode are best accessed by using the Emacs text editor.
However, several other text editors support the editing of org documents.

I use these voice commands to draft org-mode documents within 750 words.com.
Then, I copy and paste my dictated text into Emacs for further editing.
Yes, I am not a fanatical Emacs user; I use other tools.
I would use these other tools even if I had VS Code for my favorite text editor.
As indicated on my front page, I ardently believe Emacs is the ultimate text editor and that anyone serious about working with text and most computer code will eventually find themselves using Emacs.
I sure wish I had started using Emacs a decade earlier.

The current progression is for people to start out using VS Code, and then they might switch to using Vim.
After a few years of Vim, they finally realize how crappy Vimscirpt is and then switch to Emacs.
However, a recent report demonstrated how computer science students could start by using Emacs within a few weeks, thereby skipping the unnecessary phases of moving through the VS Code and then Vim before reaching Emacs.

## Usage
After the commands have been uploaded, you can utilize them straight away.
Simply activate Voice In by using a keyboard shortcut and dictate the command.

## Installation
The commands are mapped to the text that is actually inserted.
Each command is paired with the inserted text on a single line in of a comma separated value file.
Use the bulk ad button in Voice In Plus to upload these commands into your collecton of custom commands.

## Contents of the library

- org-mode file headers
- table templates
- org-babel code blocks
- 30 TODO's with priorites
- 600 TODO's with priorities and time esitmates

## Related repos
See [Voice Computing section of landing page](https://github.com/MooersLab/MooersLab?tab=readme-ov-file#voice-computing)

## Rules for develop voice commands

### Pick word combinations rarely used in normal prose
The basic rule for developing a voice command is to pick a word combination that is very unlikely to be used in one's prose.
This choice can avoid the accidental insertion of an unintended set of words.
For example, using the voice command "to do" to insert an org-mode TODO is pretty pointless because this phrase is used frequently in my prose.
Instead, I came up with the command ''priority'' and then the associated alphanumeric code for the priority. 
It is pretty unlikely that I will say the command "priority A1" in my usual prose.

### Pick word combinations that do not contain other commands
If you pick a word combination with a subset of words already assigned to another command, the commands will collide, and you will not get the intended effect.
It is better to pick a synonym for the new command than include the old one.

### Use verbs are prefaces
I use the verb "insert" in front of the computer code that I want to insert.
I use the verb "expand" to expand a person's first name into their full name and to expand acronyms into their full term.

### Test the commands
Like other forms of computer code, test the Voice In commands to ensure you get the intended effect.
The speed with which you vocalize a command has a significant impact.
You may find that you have to verbalize the command at high speed to avoid inserting just the first word of the command rather than the entire command.

## org-mode TODO voice commands with alphanumeric priorities
One primary deficit with the org-mode priority system is that it does not directly support using alphanumeric codes for prioritizing tasks.
The default is to use A, B, and C as the three property categories.
Most time management books suggest putting your to-do items into four quadrants.
Generally, items that would fall in category D are things that you should not be doing now, so why waste the effort on setting up this category?
You can configure in the header of an org document to use a different range of letters for assigning priorities to tasks.
Alternatively, you can use a range of numbers.

Unfortunately, org-mode does not directly support alphanumeric priorities.
If you assign tasks priorities A1 through A5, B1 through B5, and C1 through C5, sorting of the list of tasks will lead to A1, B1, and C1 being at the top of the list.
To get around this problem, I limit the A priorities to 1-10, the B priorities to 11-20, and the C priorities to 21-30.
Now, the sorting of the list will lead to the proper arrangement where all the A-priority items appear at the top of the list.
Please note that you probably want to limit your to-do's to three to five in each category because it is doubtful that you could accomplish ten to-dos in a day.

Just say "priority A1" and "*** TODO [#A1]" is inserted.
Next, I described the task to be completed by speech.
I coded the Voice In command such that the first letter of the first word in the description of the task will be capitalized.

The three asterisks set the heading to the third level.
I use the first level for the title of the org-mode file.
I use the second level for the date.
Then all my to-do's are under the date heading.
You can easily edit these commands to suit your needs.
 
The use of alphanumeric priority codes as advocated in [''Time Power''](https://www.amazon.com/Time-Power-Revolutionary-Management-Professional/dp/0060914904) by Charles Hobbs, a classic book on time management.
Most popular time management schemes are derivatives, but it is best to start with this source.
This book has withstood the test of 40 years; see the testimonials on Amazon.
The system is principle-driven; some of the derived versions are not and are less effective as a result.
Setting up priorities for one's work forces one to make hard choices.
Most people do not like to make these kinds of choices.
However, by turning this practice into a daily habit, you can overcome the resistance to this hard work.

### Org-mode TODOs with time estimates

I tend to be over zealous about assembling to-do list that I can never accomplish in a day.
While you are suppose to overload the list of to-do items to a certain degree in order to push yourself, excess overloading will only discourage you.
To limit overloading of a day with too many to-dos, I developed a special set of voice commands that insert a org-mode TODO with a priority in square brackets and followed by a time estimate in parentheses.
The time estimates are in units of hours.
One could probably put this time estimate into a square bracket after the square bracket for the priority, but this second set of square brackets might confuse org-mode.

#### Time bound TODO commands

I say "timed A1 h3" to insert a A1 to-do item with a time estimate of 3 hours: `*** TODO [#A1] (3)`. 
I cannot say "timed A1 3" becuase this will result timed A13.
I pre-defined these commands in advance.
I have inlcuded fractions of hours with decimal points to the nearest quarter hour.
I made a second set of commands with h replaced by the word "hour".
The language model has a slightly easier time recognizing these commands.

The Voice In software has  difficulty dealing with the point in the decimal point, so you may find yourself having to repeat these commands a few times before you get the desired result.
Once you hit upon the correct speed with which to speak these commands, the error rate will go down.
The time estimates range from 0.25 to 5 hours.
A task that will take longer than 5 hours probably needs to be split up into two or more to-do's.

#### Alternate set of time bound TODO commands starting with the word "limit" and using "harp" for "h"
I added another set of commands for time limited TODOs.
These commands start with "limit" in place of "timed".
These use the Talon Voice phonetic code of "harp" for "h".
Therefore, say "limit B5 harp 3" for a B3 activity that would take 3 hours.
The time estimates range from 1 to 5 hours in one hour increments.
I tested all of these commands.
I mapped the returned errors to the correct commands.
I helps to used ehance your enounciation and to minimize the background white noise.

#### Groups of time-bounded TODO commands

- limit 4A 4B 4C
- limit 5A 4B 3C
- limit 6A 3B 3C
- limit 4A 3B 3C
- limit 6A 3B 1C
- limit 6A 2B 2C
- limit 5A 3B 2C

#### Idea for an alarm to limit daily todo list
It would be possible to write up some elisp code that would sum up the time estimates and sound an audible alarm when the time estimates exceed a certain limit like 8, 10, 12, 14, or 16 hours, depending on the length of your standard work day.
The audible sound could be a whistle or a siren to warn you that you overloaded your to-do list.
The wave package can provide support for audible alarms like this.
It is just a matter of coming up with the e-list code to do the summing.

### Reconciling Project TODO lists with Daily TODO lists

One problem is the reconciliation of project-based to-do lists and daily to-do list.
I have yet to address this problem in a satisfactory fashion.

Org-agenda supports this reconciliation by enabling you to maintain to-do lists inside a projects.org file.
If you assign a scheduled date for a project to-do, then it will show up in your daily to-do list.
This is convenient if you are very judicious in the assignment of scheduled dates to project to-do items.
Otherwise, you will spend a ridiculous amount of time hunting down various to-do's that you did not accomplish on the assigned day and editing their scheduled date to postpone their accomplishment.
This work can become overwhelming and has led me to abandon the use of org-agenda on several occasions.
Using the projects.org file is worth trying only after you have mastered prioritizing dos and limiting the number of to-dos per day.

However, I found that academic writing projects are so complex that I prefer to maintain the to-do list for a writing project inside the writing log that I maintain on Overleaf with the writing project.
Each running log has a section for the to-do list.
These are really overflow to-dos because they have yet to be scheduled.
This overflow to-do could also be called unscheduled to-dos.
I use the concept of the next item to be done from the getting things done approach.
At a minimum, I will add this next item to my daily to-do list.

I could probably use the projects.org file if I could wean myself off Overleaf.
I find this hard to do because I have a streamlined workflow on Overleaf.
I am very reluctant to abandon something that is working so well.
In addition, I can share my access to my writing log with my collaborators.
This is harder to do inside Emacs because the collaborator must be an Emacs user.

### Overflow to-dos
If your tasks are stored in a single org-mode file for the month, semester or year, you can move some of excess your to-do items to later days in the week or month. 
You could assign a priority to the task that is just at the letter level and then add a number on the day that you plan to do that task.

However, your priorities will probably change from day to day.
There has a danger that the todos that are assign to dates in advance will probably wind up being heavily edited once that day is reached.
To avoid having to rewrite or edit these to-do's extensively every day, you can store these to do's in a list.

If you do not assign a priority to these items, then Charles Hobbs calls this list the "grasscatcher list". 
You can call it the overflow list or whatever you like.
You can store this overflow list at the top or bottom of your org-mode task.org file.
You can navigate to the bottom of this file very quickly with the control-> command and Emacs.
If you find moving selected tasks from the list back up the page to the current onerous, you could store this overflow list in a separate org file and then copy a group of to-do's from this file opened in parallel buffer for pasting into your task.org file.
