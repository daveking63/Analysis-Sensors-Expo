# Analysis-Sensors-Expo

<h3>Introduction</h3>

The genesis of this project is two fold.  

<ol>
    <li> I'm interested in the "sensor market," especially current thoughts about the roles of <i>AI/machine learning</i>, <i>edge computing</i>, and the <i>Internet of Things (IoT)</i> in this market. As this year's <a href="https://www.sensorsexpo.com/show-overview">brochure and online program</a> described, the Sensors Expo/Conference is "...the largest (international) gathering of engineers and engineering professionals involved in sensors and sensing-related technologies... (enabling them) to explore today's sensor technologies and find the solutions to tomorrow's sensing challenges." An analysis and mining of the <a href ="https://sensorsexpoconference2018.sched.com/list/descriptions/">conference content</a> could potentially provide clues about the state of the market and it's future evolution.</li>
    <li> I have a general interest in data analysis and mining, especially as they apply to: <i>text</i>, <i>topic</i>, and <i> social media</i> content. In the past I've performed analyses of this sort on a variety of datasets, including other conference programs, Rap music, and political tweets (to name a few) with a focus on understanding how you determine the underlying features of the corpus, as well as changes occurring overtime.</li>
</ol>

<h3>Datasets</h3>

Normally, in an analyses of this sort, I would have used a variety of tools (like Python's Beautiful Soup) to scrape the content from the relevant HTML pages associated with the conference content.  Because of the structure of the HTML tags, this couldn't really be done with the underlying pages. As a consequence, I decided to: (1) simply copy the text content from the displayed listings, (2) store the content in a text file, (3) create a program to extract the important details from this file (i.e. track names, session titles and abstracts, session talks and titles, and speaker names with positions and companies), and (4) store the extracted results in a larger python dictionary which for purposes of simplicity was split into two smaller dictionaries -- one containing the titles and abstracts and a second containing the speaker information. The flow of this overall process is depicted in Figure 1:

<img src="https://github.com/daveking63/Analysis-Sensors-Expo/blob/master/analysis%20of%20sensor%20expo%20and%20conference.jpg" height=530 width=955>

<h3>Analysis</h3>

The analysis of the data takes place in 3 stages:

<ul>
    <li>Textual Analysis of the titles and abstracts</li>
    <li>Topic Analysis of the abstracts *** Still in process</li>
    <li>Network Analysis among the topics, clusters and tokens (in this case lemmas), followed by the network structure among speakers, companies and topics *** Still in process</li>
</ul>

These analysis and their results are contained in 3 separate iPython notebooks. I've chosen this narrative structure because it makes it easier to understand the individual processes. Note: The notebooks are provided in two forms - iPython notebook and a Python program version.
