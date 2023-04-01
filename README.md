# Ranked-Search-Engine

# Brief Description
A simple search engine that uses a pre-defined corpus to create an inverted index. This index is used to search for query terms in the corpus.

# How-to-Run
<pre>
Prerequisites:  
	Python 3.9

Step 1. Download Required Library/Modules  
	a) pip install nltk  
	b) pip install bs4  
	c) pip install Flask  

Step 2.  
	Modiy line 23 of engine.py to match the  
	relative folder that contains the folders of domains.  
	By default, it is set to 'developer/DEV'  

Running Index (Expected time: ~2-3 hours):  
	- python3 engine.py

Running Search Engine:  
	Terminal GUI  
		-python3 search.py  
	Web GUI  
		// Does not work on openlabs  
		// Local machine with IDE( VSCode ) is recommended  
		- python3 app.py  
</pre>
# Detailed Description

The pre-defined corpus (for CS 121) contained about 56,000 documents. Engine.py is used to parse each JSON file, extract key information such as word and document frequency, to compute TF-IDF score. Certain information will be stored in several files. These include the document's URL and a list of stopwords. Key information, such as word and document frequency, important text (Bold, Heading, Title), and the word's TF-IDF score, will be stored in a inverted index in the format:
```{Word: Information}```

Search.py will retrieve the user's query and parse it. Using the inverted index created in Engine.py, it will rank the top 10 documents found under harsh time constraints and having a query response under 300ms. The "ranking system" will used the pre-processed TF-IDF score. 

In order to achieve the 300ms benchmark, several techniques were utilized. These techniques include the optimization of intersection, usage of the Shelve module for the storage of inverted index, and linecache module. 
	
