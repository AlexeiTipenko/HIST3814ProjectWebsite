# Understanding the War Diaries

Before diving deep into the project, I was curious to see how successful Tesseract to perform OCR (object character recognition) on the 80 photographs in the collection. The results were quite disappointing. Here is an example of a text file converted using Tesseract:

![Image of a text file](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/blob/master/war_diaries_ocr/e001518037.jpg-ocr.txt)

If you look through all the [text files](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/tree/master/war_diaries_ocr), you can see that all of them are of the same quality. Unfortunately, Tesseract and other OCR tools are simply not good enough to accurately transcribe the these photographs. The only solution here is to transcribe them all by hand.

Two of my classmates, Lauren Rollit and Amanda Ngan worked with me to transcribe all 80 of the original photographs into separate text files. Lauren was responsible for transcribing the first 58 documents. I transcribed the next 12, and Amanda transcribed the remaining 10. The transcribed documents can be found [here](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/tree/master/all_transcribed_diaries).

Before working on cleaning the files, I spend a lot of time looking through the transcribed files to understand what insights I can get from them. One thing was immediately clear from the start, I could not throw all the files into one and start cleaning the whole file. The first thing to note is that all the files fell into one of three broad categories: a normal diary entry, an outlier (different format) and a cover page that contained the volume numbers. I also noticed that about a third of the documents were not from the 14th hospital at all. These documents were from the 10th Canadian hospital. I noticed this by looking at the location documented either on the top of bottom of every document. The documents from the 10th hospital also had a different format. They were written by a different author who documented locations more frequently and was in the habit of documenting every event with only one date.

This was the key difference between the documents from the two hospitals. The author from the 14th hospital basically never wrote down the location of the events, and almost always had two dates documented for every event. I made the assumption that the first date was the documented date of the given event. I deduced this from the fact that this date often corresponded to multiple events and the second date was also usually a few days earlier. Because the structure of the documents from the hospitals varied a good deal, I decided to separate the ones from the 10th hospital and focus on working with only the ones from the 14th hospital.

Based on the specific documents I was working with, I found some consistent patterns that I can use to help me understand the contents of the diaries on a macro level. These included the documented date, event description, event date and the count of the various workers at specific points in time. The data on the count was also separated into a different file to keep everything organized.

Here is a list of steps I tool to organize the data:

    1) Combine all transcribed text documents into one file using the following command:
        cat * > 1-merge_initial.txt

    2) Trim the redundant and unnecessary data from the initial text file and add "DOC#:XXXX" before each section to know which original document I'm dealing with. (2-merge_trim.txt)

    3) Separate the trimmed text file into 3: 3-main_pages.txt, 4-outliers_pages.txt and 5-volume_pages.txt.

     The main mages file consists of the bulk of the data that I was working with. The other two were used as references. They can be useful for future analysis. 
