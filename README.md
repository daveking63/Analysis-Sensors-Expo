# Analysis-Sensors-Expo
Analysis of the content and speakers at 2018 Sensors Expo in San Jose from June 26-28.

<h3>Introduction</h3>

According to the official <a href="https://www.sensorsexpo.com/show-overview">conference description</a>:

"Sensors Expo & Conference is the largest gathering of engineers and engineering professionals involved in sensors and sensing-related technologies. For over 30 years, more than 6,400 professionals gather from across the nation and 40+ countries to explore today's sensor technologies and find the solutions to tomorrow's sensing challenges."

This year the conference took place in San Jose from June 26-28, 2018. A listing of the <a href ="https://sensorsexpoconference2018.sched.com/list/descriptions/">conference contents</a> provided details about the conference tracks, sessions, talks and speakers. This analysis is broken into two parts. First, it examines the lexical content of the key ideas and topics being presented at this years conference. This part of the analysis is basically completed, Second, it delves into the speakers - their titles, companies, and the key ideas they covered in their talks. This section is not quite underway (but will appear shortly).

<h3>Datasets</h3>

Normally, in analyses of this sort, I would have used a variety of tools (like Python's Beautiful Soup) to scrape the content from the relevant HTML pages associated with the conference content.  Because of the structure of the HTML tags, this couldn't really be done with the underlying pages. As a consequence, I decided to: (1) simply copy the text content from the displayed listing, (2) store the contents in text files, (3) create a program to extract the important details from these files (i.e. track names, session titles and abstracts, and speaker names, positions, and companies), and (4) store the extracted results in a set of a python dictionaries for further analysis, as well as converting the dictionaries into a couple of json files. As usual, this took a substantial amount of manual work aided by Excel and a <a href="https://www.emeditor.com">text editor</a> to work through the errors and inconsistencies in the data.

<h3>Analysis of the Lexical Content</h3>

Originally, I wanted to employ a tool called <a href="https://info.leximancer.com/company/">Leximancer</a> from a company by the same name to do the content analysis. According to the advertising, it is distinguished by a number of key features - no training sets or key term dictionaries, concepts not keywords, fast, no human bias, multiple exports, insight dashboard, etc. Unfortunately, I don't own a commercial copy (little pricey for the amateur data scientist who isn't attached to an educational institution) and the 7-day trial version emblazons the company name across key visual outputs. Consequently, I reverted to a series of Python modules (NLTK and Sklearn) that I've used on a variety of projects (analyzing other conference programs, rap music, political tweets, etc.) along with other Python modules aimed at doing network analysis. 

<h3>Lexical Analysis of Session Abstract Lemmas: Code and Results</h3>

After running a bit of analysis on the talk and session titles, I decided to focus on the session abstracts as a means to understand the basic content and topics addressed by the conference.  Additionally, after looking at various types of tokens (e.g. lowercase, non-stop alphanumeric terms or lowercase, non-stop stems, etc.), I decided to concentrate on the (1-3 gram) lemmas extracted from the individual abstracts.  The basic flow of this analysis is depicted in Figure 1:

<img src="https://github.com/daveking63/Analysis-Sensors-Expo/blob/master/analyzingSensorExpoProgram.png" alt="Figure 1. Lexical Analysis">

Within this figure, they key programs are noted in bold. They are provided in this repository and include:

<ol>
  <li><i>trkDictSetUp.py</i> - Converts a text representation of the Expo program</li> into a Python dictionary containing the hierarchy of tracks (with ids and titles), sessions (with ids, titles and abstracts) and talks (with ids and titles). Note: speaker data is held in another dictionary.</li>
  <li><i>trkAnalysisExamples.py</i> - Simple set of examples illustrating how to navigate the hierarchy to obtain information about the various tracks and sessions.</li>
  <li><i>sessAbstractLemAnalysis.py</i> - Produces a Python dictionary containing and entry for each session which in turn contains a an id along with both a list of tokens for each type (words, lowercase, alphas, nonstops, stems and lemmas) found in the abstract as well as a summarized count of the list (e.g. {'word1':N1, 'word2':N2, ...,'wordN':Nn} or {'lemma1':N1, 'lemma2':N2, ...,'lemmaN':Nn})
  <li><i>lemTopics.py</i> - Using various modules from sklearn and matplotlib (both part of sciPy), this part of the analysis employs the dictionary of session lemmas found in the previous step to understand which tracks and sessions share similar content. Before performing the topic analysis, simpler forms of analysis were performed to guide the topic extraction.  Included were correlation, cluster/dendogram, and chi-square tests.
  <li><i>topicNetworks.py</i> - While this is yet to be completed, the basic goal is to provide a network display showing the links among various lemmas by topic, track and session. The display is somewhat similar to the display provided by the Leximancer system.</li>
</ol>
Given the complexities of these analyses, I've provided a narrated form of the processes and programs depicted in Figure 1. This narration, which is found in the Juypter iPython file labeled <a href=""><i>Topical Content: Lexical Analysis of Lemmas</i></a>. It provides not only a step-by-step rendition of these processes but also a step-by-step explanation of the results.
