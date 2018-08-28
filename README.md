# Analysis-Sensors-Expo
Analysis of the content and speakers at 2018 Sensors Expo in San Jose from June 26-28.

<h3>Introduction</h3>

According to the official <a href="https://www.sensorsexpo.com/show-overviewconference">conference description</a>:

"Sensors Expo & Conference is the largest gathering of engineers and engineering professionals involved in sensors and sensing-related technologies. For over 30 years, more than 6,400 professionals gather from across the nation and 40+ countries to explore today's sensor technologies and find the solutions to tomorrow's sensing challenges."

This year the conference took place in San Jose from June 26-28, 2018. A listing of the <a href ="">conference contents</a> provided details about the conference tracks, sessions, talks and speakers. This analysis focuses on these details. First, it examines the lexical content of the key ideas and topics being presented at this years conference. Second, it delves into the speakers - their titles, companies, and the key ideas they covered in their talks.

<h3>Datasets</h3>

Normally, in analyses of this sort, I would have used a variety of tools (like Python's Beautiful Soup) to scrape the content from the relevant HTML pages associated with the listings.  Because of the structure of the HTML tags, this couldn't really be done with the detailed listing. As a consequence, I decided to: (1) simply copy the text content from the displayed listing, (2) store the contents in a text files, (3) create a program to extract the important details (i.e. track names, session titles and abstracts, and speaker names, positions, and companies), and (4) store the extracted results in a set of a python dictionaries for further analysis, as well as converting the dictionaries into a couple of json files. As usual, this took a substantial amount of manual work (aided by Excel and a text editor - in my case <a href="www.emeditor.com">EmEditor</a>) to work through the errors and inconsistencies in the data.

<h3>Analysis of the Lexical Content</h3>

Normally, I would employ Python's NLTK and a series of other SciPy tools to perform the lexical and topical analysis.  As a bit of an experiment, I decided to use a tool called <a href="https://info.leximancer.com/company/">Leximancer</a> from a company by the same name. According to the advertising, it is distinguished by the following features:

<ul>
<li>Minimal set</li>
<li>No training sets or key term dictionaries</li>
<li>No human bias in analysis</li>
<li>Finds Concepts in Context, not keywords</li>
<li>Useful results fast</li>
<li>Concept and Network cloud visualisations</li>
<li>Sentiment lens</li>
<li>Concept exploration</li>
<li>Concept based document query</li>
<li>Multiple exports include:
<li>Insight Dashboard Report - Insight Dashboard Report & Concept Thesaurus
 </ul>
