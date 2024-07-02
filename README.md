![Version](https://img.shields.io/static/v1?label=org-mode-voice-in&message=0.1.1&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

# org-mode-voice-in

## Introduction
The CSV file in this repository contains the library of org-mode-related voice commands for the browser-based Speech-to-Text plugin Voice In Plus for Google Chrome and Microsoft Edge.
The commands include text replacements for misinterpreted words related to org and boilerplate code for making to-do lists.
The org commands cannot be executed directly in Emacs, but they can be used indirectly via GhostText.
Some of the org code may run inside the web version of VS Code.

## Work in progress
I plan to include more mode org-mode-related code snippets.


## Background
The utilization of these custom commands requires a subscription to Voice In Plus.
The fee is modest, and it has been one of the best returns on investment I have made in the past year.
My use of it has less friction than Serenade or Talon Voice.


Voice In Plus works in any text area, such as in:

- An Emacs session linked to the text area in a web browser with GhostText running. The text area is where Voice In Plus can operate. GhostText mirrors the transcribed text in an Emacs buffer.
- Org-mode documents in JupyterLab. You can use the library to compose the org-mode document and then run it later in Emacs to debug it.
- Markdown documents are in GitHub while in editing mode.
- Markdown documents in Jupyter Lab. 
- Markdown documents in 750words.com.
- Markdown documents in Write Honey (writehoney.com) (e.g., free account for life with no daily word limit, an alternative to 750words.com).
- Code and markdown cells in Jupyter notebooks.
- tex documents on Overleaf.com
- Gmail.
- Outlook web mail.
- Might work in a docker-hosted Emacs.


Org-mode is an advanced form of Markdown that has strong support for the following activities:

- Outlining.
- Time and project management through the org-agenda package.
- Knowledge Management through the zettelkasten method implemented in the org-roam package for Emacs.
- Academic manuscript preparation with exports to PDF and several alternative packages for inserting citations.
- The preparation of blog posts that are exported to HTML.
- Book preparation leveraging the features of LaTeX.
- The preparation of Reveal.js style slides in HTML with org-real.
- Tables that enable computations to be run automatically on a by-row or by-column basis.
- Support for literature programming with source blocks that can be executed with the output included in the org document.

All the org-mode features are best accessed using the Emacs text editor.
Org-mode was developed for Emacs.
However, other text editors (e.g., VS Code, NeoVim) now support org documents.


I use these voice commands to draft org-mode documents within 750 words.com.
Then, I copy and paste my dictated text into Emacs for further editing.

I am not a fanatical Emacs user; I use other tools.
I would use these other tools even if VS Code was my favorite text editor.

As indicated on my front page, I ardently believe Emacs is the ultimate text editor and that anyone serious about working with text and most computer code will eventually use it.
I wish I had started using Emacs a decade earlier.

The current progression is for people to start using VS Code and switch to Vim when they want more control over their editor.
After a few years of Vim, they finally realized how much fun they were missing by not configuring their editor with Emacs LISP.
Talks ( []() and []() ) by Professor Marcus Birkenkrahe demonstrated how computer science students could start using Emacs within a few weeks, skipping the long phases of moving through VS Code and Vim before reaching Emacs.

## Usage
After the commands have been uploaded, you can utilize them straight away.
Simply activate Voice In by using a keyboard shortcut and dictate the command.

## Installation
The commands are mapped to the text that is inserted.
Each command is paired with the inserted text on a single line in a comma-separated value file.
Use the bulk ad button in Voice In Plus to upload these commands to your collection of custom commands.

## Contents of the library

- org-mode file headers
- table templates
- org-babel code blocks
- 30 TODO's with priorities
- 600 TODOs with priorities and time estimates

## Related repositories
See [Voice Computing section of landing page](https://github.com/MooersLab/MooersLab?tab=readme-ov-file#voice-computing)

## Rules for developing voice commands

### Pick word combinations rarely used in regular prose
The basic rule for developing a voice command is to pick a word combination that is very unlikely to be used in one's prose.
This choice can avoid the accidental insertion of an unintended set of words.

For example, using the voice command "to do" to insert an org-mode TODO is pointless because I frequently use this phrase in my prose.
Instead, I created the command ''priority'' and the associated alphanumeric code for the priority. 
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
You may have to verbalize the command at high speed to avoid inserting just the first word rather than the entire command.

## org-mode TODO voice commands with alphanumeric priorities
One primary deficit with the org-mode priority system is that it does not directly support using alphanumeric codes for prioritizing tasks.
The default is to use A, B, and C as the three property categories.
Most time management books suggest putting your to-do items into four quadrants.
Generally, items that would fall in category D are things you should not be doing now, so why waste the effort setting up this category?
You can configure in the header of an org document to use a different range of letters for assigning priorities to tasks.
Alternatively, you can use a range of numbers.

Unfortunately, org-mode does not directly support alphanumeric priorities.
If you assign tasks priorities A1 through A5, B1 through B5, and C1 through C5, sorting the list of tasks will result in A1, B1, and C1 being at the top of the list.
To get around this problem, I limit the A priorities to 1-10, the B priorities to 11-20, and the C priorities to 21-30.
Now, sorting the list will lead to the proper arrangement where all the A-priority items appear at the top of the list.
Please note that you probably want to limit your to-do's to three to five in each category because it is doubtful that you could accomplish ten to-dos daily.

Just say "priority A1" and "*** TODO [#A1]" is inserted.
Next, I described the task to be completed by speech.
I coded the Voice In command such that the first letter of the first word in the task description will be capitalized.

The three asterisks set the heading to the third level.
I use the first level for the title of the org-mode file.
I use the second level for the date.
Then all my to-do's are under the date heading.
You can easily edit these commands to suit your needs.
 
The use of alphanumeric priority codes as advocated in [''Time Power''](https://www.amazon.com/Time-Power-Revolutionary-Management-Professional/dp/0060914904) by Charles Hobbs, a classic book on time management.
Most popular time management schemes are derivatives, but it is best to start with this source.
This book has withstood the test of 40 years; see the testimonials on Amazon.
The system is principle-driven; some of the derived versions are not and are less effective.

Setting up priorities for one's work forces one to make hard choices.
Most people prefer to avoid making these kinds of choices.
However, by making this practice a daily habit, you can overcome resistance to this hard work.

### Org-mode TODOs with time estimates

I tend to be overzealous about assembling a to-do list I can never accomplish in a day.
While you are supposed to overload the list of to-do items to a certain degree to motivate yourself, excessive overloading will only discourage you.
To limit the overloading of a day with too many to-dos, I developed a special set of voice commands that insert an org-mode TODO with a priority in square brackets and followed by a time estimate in parentheses.
The time estimates are in units of hours.
One could put this time estimate into a square bracket after the square bracket for the priority, but this second set of square brackets might confuse org-mode.

#### Time-bound TODO commands

I say "timed A1 h3" to insert an A1 to-do item with a time estimate of 3 hours: `*** TODO [#A1] (3)`. 
I cannot say "timed A1 3" because this will result in timed A13.
I pre-defined these commands in advance.
I have inlcuded fractions of hours with decimal points to the nearest quarter hour.
I made a second set of commands with h replaced by the word "hour".
The language model has a slightly easier time recognizing these commands.

The Voice In software has difficulty dealing with the point in the decimal point, so you may find yourself having to repeat these commands a few times before you get the desired result.
Once you reach the correct speed for speaking these commands, the error rate will decrease.
The time estimates range from 0.25 to 5 hours.

A task that will take longer than 5 hours needs to be split up into two or more to-do's.
the second to do should probably be translated to the next day.
The reality is that you should probably not spend more than 5 hours on any particular task on a given day anyway because you will lose momentum after 4 and 1/2 hours.
If you are an academic and have to make progress on multiple writing projects, time limits of three to 5 hours per day are practical.


#### Alternate set of time-bound TODO commands starting with the word "limit" and using "harp" for "h"
I added another set of commands for time-limited TODOs.
These commands start with "limit" in place of "timed".
These use the Talon Voice phonetic code of "harp" for "h".
Therefore, say "limit B5 harp 3" for a B3 activity that would take 3 hours.
The time estimates range from 1 to 5 hours in one hour increments.
I tested all of these commands.
I mapped the returned errors to the correct commands.
I helps to used ehance your enounciation and to minimize the background white noise.

#### Groups of time-bounded TODO commands mapped to one voice command

The above approach has advantage that after a new TODO item is inserted, the cursor will be positioned correctly and the first letter of the first word will be capitalized when you dictate the action to be taken.
The disadvantage of the above approach that you have to speak out each item one at a time as you need them.
An alternative approach is to insert a group of prioritized to-do items with a default duration of 1 hour.
You will have to edit the duration or time estimate and you will have to handle the capitalization of the first letter of the first word of task.
The advantage of this approaches that you are starting out with a reasonable number of TODO items.
Below is a list of various combinations of A, B and C TODOs .

- limit 4A 4B 4C
- limit 5A 4B 3C
- limit 6A 3B 3C
- limit 4A 3B 3C
- limit 6A 3B 1C
- limit 6A 2B 2C
- limit 5A 3B 2C

For example, you would say "limit 5a3b2c" or "limit 5a 3b 2c" to insert the following list:

```org-mode
*** TODO [#A1] (1)
*** TODO [#A2] (1)
*** TODO [#A3] (1)
*** TODO [#A4] (1)
*** TODO [#A5] (1)
*** TODO [#B11] (1)
*** TODO [#B12] (1)
*** TODO [#B13] (1)
*** TODO [#C21] (1)
*** TODO [#C22] (1)
```

You could use one of these predefined sets of to-do's as a means of nucleating your current day's list.
If you wish to add a 6th A priority to-do, you can use the corresponding time-bound to-do command `limit A6 harp 1` with the cursor at the end of the line for A5.
This will insert the new to-do into the existing list at the appropriate position.



#### Idea for an alarm to limit daily todo list
It would be possible to write up some elisp code that would sum up the time estimates and sound an audible alarm when the time estimates exceed a certain limit like 8, 10, 12, 14, or 16 hours, depending on the length of your standard work day.
The audible sound could be a whistle or a siren to warn you that you have overloaded your to-do list.
The wave package can provide support for audible alarms like this.
It is just a matter of creating the elisp code to do the summing.

### Reconciling Project TODO lists with Daily TODO lists

One problem is the reconciliation of project-based to-do lists and daily to-do list.
I have yet to address this problem in a satisfactory fashion.

Org-agenda supports this reconciliation by enabling you to maintain to-do lists inside a projects.org file.
If you assign a scheduled date for a project task, it will appear in your daily to-do list.
This is convenient if you are very judicious in the assignment of scheduled dates to project to-do items.
Otherwise, you will spend a ridiculous amount of time hunting down various to-do's you did not accomplish on the assigned day and editing their scheduled date to postpone their accomplishment.
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
If your tasks are stored in a single org-mode file for the month, semester, or year, you can move some of your excess to-do items to later days in the week or month. 
You could assign a priority to the task that is just at the letter level and then add a number on the day that you plan to do that task.

However, your priorities will probably change from day to day.
There is a danger that the to-dos assigned to dates in advance will probably be heavily edited once that day is reached.
To avoid having to rewrite or edit these to-dos extensively every day, you can store them in a list.

If you do not assign a priority to these items, then Charles Hobbs calls this list the "grasscatcher list". 
You can call it the "overflow list" or whatever you like.
You can store this overflow list at the top or bottom of your org-mode task.org file.
You can navigate to the bottom of this file very quickly with the control-> command in Emacs.
If you find moving selected tasks from the list back up the page to the current onerous, you could store this overflow list in a separate org file and then copy a group of to-do's from this file opened in a parallel buffer for pasting into your task.org file.

## Sources of funding

- NIH: R01 CA242845
- NIH: R01 AI088011
- NIH: P30 CA225520 (PI: R. Mannel)
- NIH: P20 GM103640 and P30 GM145423 (PI: A. West)

## Update history

|Version      | Changes                                                                                                                                    | Date                 |
|:-----------:|:------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------:|
| Version 0.1.1 |  Added some text replacements. Added and update table.                                                                                   | 2024 July 2         |

