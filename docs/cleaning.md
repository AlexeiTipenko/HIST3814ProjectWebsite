# Cleaning Data

The cleaning process for the project was a combination of manual editing and the "Find and Replace" option found in most text editors. I personally decided to use atom as my text editor. The find and replace functionality within atom is quite powerful and it has regular expression functionality build in as well.

At the beginning of the cleaning process, there were certain issues that could not be fixed using any tool. For example, there was no way for a tool to recognize when an event spanned multiple lines. I also needed to add the documented dates to every single line to ensure consistency. I couldn't find a regular expression that could help me perform these two tasks.

Once there was a general consistency in the text file with every line consisting of 2 dates and an event, I began to actively use regex to do the rest of the cleaning.

A common way of using regex is to use sed commands. Here is an example.

    sed -r -i.bak 's/(,)( [0-9]{4})(.+)/\2/g' index.txt

This is definitely a valid method, but I found that using the find and replace option inside atom was both easier and more intuitive. All I had to do was enter my regex command into the find window and enter another command to select the groups I want to keep for the replacement in the replace window. Every time I performed a regex operation, I could clearly see if the operation was successful. If it wasn't, I would simply undo the past command.

Here is a list of all the commands I used to clean my text file:

    1)  ([a-zA-Z][\.][a-zA-Z][\.])([\040])(\w+)
    2)  ([\040])([a-zA-Z])([\.])([\040])(\w+)
    3)  ([\040])(\bC\.A\.M\.C\.)(Depot)
    4)  (\b\d[/]\d\d[/]\d\d)
    5)  (\d\d[/]\d\d[/])(\d\d)
    6)  (\d\d[/]\d[/])(\d\d)
    7)  ([^\d])(\d[/]\d[/])(\d\d)
    8)  (,)(\d\d[/]\d\d[/])(\d\d\d\d)(\.)
    9)  (,)(\d\d[/]\d[/])(\d\d\d\d)(\.)
    10) ([\040])([a-zA-Z][\.][a-zA-Z][\.][a-zA-Z][\.][^\s\.]+)([\040])
    11) ([\040])([a-zA-Z][\.][a-zA-Z][\.][^\s\.]+)([\040])
    12) ([\040])([a-zA-Z][\.][^\s\.]+)([\040])

Most of these regular expressions do very similar things. The idea was to create a series of groups that equate to the exact format of the text I wanted to change and then simply replace them with the groups necessary.

For example, I wanted to find all instances of 'X.X. WORD'. This exact format is almost always mapped to a name, with some exceptions. My goal was to remove the space between the last period and the name for each instance of this pattern. So I created this regular expression:

    ([a-zA-Z][.][a-zA-Z][.])([\040])(\w+)

All it says is to find a group that has a letter (1), period (1), letter (2), period (2), then have another group following that represents a space, and then a final group that represents a whole word of any length. After specifying this group, all I had to do was replace the 3 groups with the first and the third.

    $1$2

 After executing this find and replace operation, the letters, periods and one word will stay, but the space in between would be deleted. This is exactly what I wanted and I didn't have to manually search through the whole text file to make all these changes. The rest of the regular expressions worked in an almost identical way.

 Sometimes, even regex wasn't necessary. There were many words and sentences that I could find and replace with another version of them. For example '.SEAFORD' could be replaced with '. Seaford', or 'Hsp' could be replaced with "Hospital".

 The final cleaning process involved using open refine and trifacta to merge certain words and phrases. Open refine did not work when I tried processing the entirety of the event data. There was simply too much data. I was able to make some small changes using the key collision method, however everything froze for the nearest neighbor method. To get more use out of open refine, I extracted all the names mentioned in the overall text file and did separate cleaning on it. This file was much smaller, and I was able to merge several names together. Trifacta is a software application that also allowed me to tweak a few things in my overall csv file. I was able to rename a few sentences that were almost identical to others to create a more accurate distribution of common phrases.

 The end result was [this file](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/blob/master/cleaning/6-HOSP_14_main). There is no way to get a completely clean file without doing everything by hand, but I would say that the great majority of the data has been transcribed and cleaned properly. 
