Technical Assignment, Question-2


This document explains my approaches, the methods I have used, a few clarifications, and some roadblocks I faced while attempting this question.


I already had a beginner-level knowledge of Python and some of its libraries. However, web scraping was new for me. I installed the necessary libraries, and went ahead learning about web scraping from the video resource given along with the question. 
Seeing that we had a bonus for extracting the SOC database, I decided to pull the contents of the SOC database itself.


Major Roadblocks Faced: 
I had initially decided to extract all the project titles from the main page of SOC. I succeeded in extracting those; however, I faced issues when extracting the individual project hyperlinks from the anchor tags. I spent quite some time grappling with it, and eventually gave up, unable to find the error as to why I wasn't getting my expected output. 
I had even decided to switch to another easier-to-scrape website and even zeroed upon http://books.toscrape.com/.
I had even started working on the 2nd website, when it struck me that I could use another approach on the SOC page. I could directly extract the links of the individual projects first, and then extract every detail from the particular project. So I tried again, and this time, I succeeded in establishing connections with individual projects through the main page. 
I extracted the project name from the heading tag. One unusual error I faced was being caused by the "The Watchdogs" SOC project. My code seemed to terminate at that exact project every time, and I could not find out why. However, that error disappeared as mysteriously as it had appeared. The next roadblock I faced was extracting the mentors' details and the number of mentees from the page. I could not pinpoint the exact div I needed to access, using my code. Brainstorming again, I looked through the HTML code of a few project pages, and realized that in each case, it was the 4th and 5th occurrence of the <ul> (unordered list) tag, which contained the mentor and mentee details. Thus, I wrote my code accordingly and extracted all the required information. 
The rest of it was pretty much smooth sailing, for the most part. I was able to get done with the rest of the code without much trouble.








Explanation of the code: 
As instructed, I used the requests library to extract the HTML content of the websites, and the beautifulsoup library, to parse the extracted HTML.
I deemed it feasible to extract the project name, mentor's name, number of mentees, the domain of the project, and the link to the project page from the parsed data.
First, I extracted the link to the project page by accessing the appropriate div in the main SOC page. After establishing a connection with the project page, I pulled the project name from the heading tag, extracted mentor-mentee information from the unordered list, and, subsequently, the paragraph tags. I looped through and added the details in their corresponding lists, which I had declared first up in my code. I also coded up to find out the number of mentors for each project, which was relatively easy.
I then created a Pandas data frame from the above-obtained lists, containing the columns Project Name, Domain, Mentors Name, Mentors Number, Mentees Number and the Link to the Project. I also did some data processing on it, such as removing the roll numbers from the mentors' names, replacing "&" with "," in mentors' names, formatting the names appropriately; in title case, and also removing duplicate and null values from the data frame. 
I finally exported the created data frame into a CSV file, named "SOC Data". I chose the CSV format for sharing data due to its simplicity, compatibility, its light-weightedness and comprehensive support across various applications and platforms.




I overall enjoyed working on this question, and I also learnt about web scraping in the course of solving this question.