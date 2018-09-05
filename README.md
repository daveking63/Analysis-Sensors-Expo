# Analysis-Sensors-Expo

<h3>Introduction</h3>

The genesis of this project is two fold.  

<ol>
    <li> I'm interested in the "sensor market," especially current thoughts about the roles of <i>edge computing</i> and the <i>Internet of Things (IoT)</i> in this market. As this year's <a href="https://www.sensorsexpo.com/show-overview">program</a> described, the Sensors Expo/Conference is "...the largest (international) gathering of engineers and engineering professionals involved in sensors and sensing-related technologies... (enabling them) to explore today's sensor technologies and find the solutions to tomorrow's sensing challenges." An analysis and mining of the <a href ="https://sensorsexpoconference2018.sched.com/list/descriptions/">conference content</a> could potentially provide clues about the state of the market and it's future evolution.</li>
    <li> I have a general interest in data analysis and mining, especially as they apply to: <i>text</i>, <i>topic</i>, and <i> social media</i> content. In the past I've performed analyses of this sort on a variety of datasets, including other conference programs, Rap music, and political tweets (to name a few) with a focus on understanding how you determine the underlying features of the corpus, as well as changes occurring overtime.</li>
</ol>

<h3>Datasets</h3>

Normally, in analyses of this sort, I would have used a variety of tools (like Python's Beautiful Soup) to scrape the content from the relevant HTML pages associated with the conference content.  Because of the structure of the HTML tags, this couldn't really be done with the underlying pages. As a consequence, I decided to: (1) simply copy the text content from the displayed listing, (2) store the content in a text file, (3) create a program to extract the important details from this file (i.e. track names, session titles and abstracts, session talks and titles, and speaker names, positions, and companies), and (4) store the extracted results in a larger python dictionary which for purposes of simplicity was split into two smaller dictionaries -- one containing the titles and abstracts and a second containing the speaker information. As usual, this took a substantial amount of manual work aided by Excel and a <a href="https://www.emeditor.com">text editor</a> to work through the errors and inconsistencies in the data.

<h3>Analysis</h3>

The analysis of the data takes place in 3 stages:

<ul>
    <li>Analysis of the Lexical structure of the titles and abstracts, followed by a topical analysis of the abstracts.</li>
    <li>Analysis of the positions and companies of the speakers</li>
    <li>Analysis of the network structure among the topics, clusters and tokens (in this case lemmas), followed by the network structure among speakers, companies and topics</li>
</ul>

These analysis and their results are contained in 3 separate iPython notebooks. I've chosen this narrative structure because it makes it simplier to understand the individual processes.
    
    After running a bit of analysis on the talk and session titles, I decided to focus primarily on the session abstracts as a means to understand the basic content and topics addressed by the conference.  Additionally, after looking at various types of tokens (e.g. lowercase, non-stop alphanumeric terms or lowercase, non-stop stems, etc.), I decided to concentrate primarily on the (1-3 gram) lemmas extracted from the individual abstracts.

<img src="https://github.com/daveking63/Analysis-Sensors-Expo/blob/master/analyzingSensorExpoProgram.png" alt="Figure 1. Lexical Analysis">

Within this figure, they key programs are noted in bold. They are provided in this repository and include:

<ol>
  <li><i>trkDictSetUp.py</i> - Converts a text representation of the Expo program</li> into a Python dictionary containing the hierarchy of tracks (with ids and titles), sessions (with ids, titles and abstracts) and talks (with ids and titles). Note: speaker data is held in another dictionary.</li>
  <li><i>trkAnalysisExamples.py</i> - Simple set of examples illustrating how to navigate the hierarchy to obtain information about the various tracks and sessions.</li>
  <li><i>sessAbstractLemAnalysis.py</i> - Produces a Python dictionary containing and entry for each session which in turn contains a an id along with both a list of tokens for each type (words, lowercase, alphas, nonstops, stems and lemmas) found in the abstract as well as a summarized count of the list (e.g. {'word1':N1, 'word2':N2, ...,'wordN':Nn} or {'lemma1':N1, 'lemma2':N2, ...,'lemmaN':Nn})
  <li><i>lemTopics.py</i> - Using various modules from sklearn and matplotlib (both part of sciPy), this part of the analysis employs the dictionary of session lemmas found in the previous step to understand which tracks and sessions share similar content. Before performing the topic analysis, simpler forms of analysis were performed to guide the topic extraction.  Included were correlation, cluster/dendogram, and chi-square tests.
  <li><i>topicNetworks.py</i> - While this is yet to be completed, the basic goal is to provide a network display showing the links among various lemmas by topic, track and session. The display is somewhat similar to the display provided by the Leximancer system.</li>
</ol>
Given the complexities of these analyses, I've provided a narrated form of the processes and programs depicted in Figure 1. This narration, which is found in the Juypter iPython file labeled <a href=""><i>Topical Content: Lexical Analysis of Lemmas</i></a>, provides not only a step-by-step rendition of these processes but also a step-by-step explanation of the results.
