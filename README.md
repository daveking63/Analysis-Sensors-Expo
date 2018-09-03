# Analysis-Sensors-Expo
Analysis of the content and speakers at 2018 Sensors Expo in San Jose from June 26-28.

<h3>Introduction</h3>

According to the official <a href="https://www.sensorsexpo.com/show-overview">conference description</a>:

"Sensors Expo & Conference is the largest gathering of engineers and engineering professionals involved in sensors and sensing-related technologies. For over 30 years, more than 6,400 professionals gather from across the nation and 40+ countries to explore today's sensor technologies and find the solutions to tomorrow's sensing challenges."

This year the conference took place in San Jose from June 26-28, 2018. A listing of the <a href ="https://sensorsexpoconference2018.sched.com/list/descriptions/">conference contents</a> provided details about the conference tracks, sessions, talks and speakers. This analysis focuses on these details. First, it examines the lexical content of the key ideas and topics being presented at this years conference. Second, it delves into the speakers - their titles, companies, and the key ideas they covered in their talks.

<h3>Datasets</h3>

Normally, in analyses of this sort, I would have used a variety of tools (like Python's Beautiful Soup) to scrape the content from the relevant HTML pages associated with the conference content.  Because of the structure of the HTML tags, this couldn't really be done with the underlying pages. As a consequence, I decided to: (1) simply copy the text content from the displayed listing, (2) store the contents in text files, (3) create a program to extract the important details from these files (i.e. track names, session titles and abstracts, and speaker names, positions, and companies), and (4) store the extracted results in a set of a python dictionaries for further analysis, as well as converting the dictionaries into a couple of json files. As usual, this took a substantial amount of manual work aided by Excel and a <a href="https://www.emeditor.com">text editor</a> to work through the errors and inconsistencies in the data.

<h3>Analysis of the Lexical Content</h3>

Originally, I wanted to employ a tool called <a href="https://info.leximancer.com/company/">Leximancer</a> from a company by the same name to do the content analysis. According to the advertising, it is distinguished by a number of key features - no training sets or key term dictionaries, concepts not keywords, fast, no human bias, multiple exports, insight dashboard, etc. Unfortunately, I don't own a commercial copy (little pricey for the amateur data scientist who isn't attached to an educational institution) and the 7-day trial version emblazons the company name across key visual outputs. Consequently, I reverted to a series of Python modules (NLTK and Sklearn) that I've used on a variety of projects (analyzing other conference programs, rap music, political tweets, etc.) along with other Python modules aimed at doing network analysis. 

<h3>Code and Results</h3>

The basic flow of the analysis is depicted in Figure 1:

<img src="pic_trulli.jpg" alt="Italian Trulli">

For those who are interested, the base code that I used has been uploaded to this repository. The code is divided into a series of programs including:

<ol>
  <li></li>
  <li></li>
  <li></li>
</ol>
        <li></li>
