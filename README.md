# org-mode-voice-in

## Introduction
Org-mode related voice commands for the browser-based Voice In.
The utilization of these custom commands requires a subscription to Voice In Plus.

## Usage
After the commands have been uploaded, you can utilize them straight away.
Simply activate Voice In by using a keyboard shortcut and dictate the command.

## Installation
The commands are mapped to the text that is actually inserted.
Each command is paired with the inserted text on a single line in of a comma separated value file.
Use the bulk ad button in Voice In Plus to upload these commands into your collecton of custom commands.

## Contents

- org-mdoe file headers
- table templates
- org-babel code blocks
- TODO's with priorites
- TODO's with priorities and time esitmates

## Related repos
See [Voice Computing section of landing page](https://github.com/MooersLab/MooersLab?tab=readme-ov-file#voice-computing)

## Rules for develop voice commands

### Pick word combinations rarely used in normal prose
The basic rule for developing a voice command is to pick a word combination that is very unlikely to be used in one's prose.
This choice can avoid the accidental insertion of an unintended set of words.
For example, it is pretty pointless to use the voice command "to-do" to insert an org-mode TODO because this phrase is used frequently in prose.
Instead, I came up with the command ''priority'' and then the associated alphanumeric code for the priority. 
It is quite unlikely that I am going to say the command "priority A1" in my normal prose.

### Pick word combintations that do not contain over commands
If you pick a word combination that has a subset of words that are already assigned to another command, then the commands will collide and you will not get the intended effect.
It is better to pick a synonym for the new command rather than to include the old one

### Use verbs are prefaces
I use the verb "insert" in front of computer code that I want to insert.
I use the verb "expand" to expand the first name of a person into their full name and to expand acronyms into their full term.

### Test the commands
Like other forms of computer code, the Voice In commands need to be tested to ensure that you get the effect that you intend.
The speed with what you vocalize a command has a big impact.
You may find that you have to verbalize the command at a high speed to avoid having just the first word of the command inserted rather than the full command.


## org-mode TODO voice commands

One major deficit with the org-mode priority system is that it does not support directly the use of alphanumeric codes for prioritizing tasks.
The default is to use A, B and C as the three property categories.
Most time management books will suggest that you put your to-do items into four quadrants.
Generally, items that would fall in the category D are things that you should not be doing now, so why waste the effort on setting up this category?
You can configure in the header of an org document to use a different range of letters for assigning priorities to tasks.
Alternatively, you can use a range of numbers.

Unfortunately, org-mode does not directly support alpha-numeric priorities.
If you assign tasks priorities A1 through A5, B1 through B5, and C1 through C5, sorting of the list of tasks will lead to A1, B1, and C1 being at the top of the list.
To get around this problem, I limit the A priorities to 1-10, the B priorities to 11-20, and the C priorities to 21-30.
Now, the sorting of the list will lead to the proper arrangement where all the A priority items appear at the top of the list.
Please note that you probably want to limit your to-do's to three to five in each category because it is highly unlikely that you could accomplish ten to-dos ins day.

Now, just say "priority A1" and "*** TODO [#A1]" is inserted.
Next, I described by speech the task to be completed.
Voice In is coded such that the first letter of the first word in the description of the task will be capitalized.

The three asterisks set the heading to the third level.
I use the first level for the title of the orgmode file.
I use the second level for the date.
Then all my to do's are under the date heading.
Obviously, you can easily edit these commands to suit your needs.
 
The use of alpha-numeric priority codes as advocated in ''Power Time'' by Charles Hobbs, a classic book on time management.
The setting up priorities to one's work forces one to make hard choices.
Most people do not like to make these kinds of choices.
However, by turning this practice into a habit, you can overcome the resistance to doing this hard work.

### TODOs with time estimates

I tend to be over zealous about assembling to-do list that I can never accomplish in a day.
The disease of being overly ambitious is built into my surname.
While you are suppose to overload the list of to-do items to a certain degree in order to push yourself, excess overloading will only discourage you.
To limit overloading of a day with too many to-dos, I developed a special set of voice commands that insert a org-mode TODO with a priority in square brackets and followed by a time estimate in parentheses.
The time estimate is in units of hours.
One could probably put this time estimate into a square bracket after the square bracket for the priority, but this second set of square brackets might confuse org-mode.

I say "timed A1 h3" to insert a A1 to-do item with a time estimate of 3 hours: `*** TODO [#A1] (3)`. 
I cannot say "timed A1 3" becuase this will result timed A13.
I pre-defined these commands in advance.
I have inlcuded fractions of hours with decimal points to the nearest quarter hour.
The Voice In software has a little difficulty dealing with the point in the decimal point, so you may find yourself having to repeat these commands a few times before you get the desired result.
Once you hit upon the correct speed with which they speak these commands, the error rate will go down.
The time estimates range from 0.25 to 5 hours.
A task that will take longer than 5 hours probably needs to be split up into two or more to-do's.

I would be cool to write up some elips code that would sum up the time estimates and sound an audible alarm when the time estimates exceed a certain limit like 8, 10, 12, 14, or 16 hours, depending on the length of your standard work day.
The audible sound should be a whistle or a siren to warn you that you overloaded your to-do list.
The wave package can provide support for audible alarms like this.
It is just a matter of coming up with the e-list code to do the summing.


