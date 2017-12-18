# complexsem
Comlexsem exam

<a id="org0d73a75"></a>

# 1

Describe the Distributional Hypothesis. Explain how the Distributional Hypothesis can be used to find semantically similar words in corpora. (3 points)

-   cite the dh
-   mention word2vec
-   cooccurences
-   


<a id="orgfe471da"></a>

# 2

Because DSMs generate ranked lists of semantically similar words, they can be seen as alternatives to manually built lexical resources such as WordNet. Explain the main differences between the lexical semantic content of WordNet and the lexical output of DSMs and discuss advantages and drawbacks of manually built lexical resources such as Wordnet and automatically generated lexical resources such as lists of semantically similar words stemming from DSMs. Can you think of an application that would fare better when using WordNet and another that would benefit more from the output of DSMs? (5 points)


<a id="orgde7e915"></a>

# 3

In this assignment you are going to gather semantically similar words using the following
types of data: [see below].

In order to gather semantically similar words, we need: A) an extraction program (for the extraction from the parallel text and, if you have chosen a different language under 1), for the monolingual text as well): a program that gathers coocurrence counts for the target words, and B) a DSM tool, a program that will compute the similarity between the coocurrence vectors for the head words we are interested in – taking the coocurrence matrix as input.  You will need to write the extraction program in Python. You will not need to program the DSM tool. For the latter, we will use available software instead.


<a id="org890ed30"></a>

## A

A monolingual corpus. You can use the corpus files that are provided as part of the DISSECT package (or the Wordspace project), for English. Or, you can also choose to extract data for a language of your choice from a corpus of your choice. I will give you extra points if you do.


<a id="orgf928908"></a>

## B

Word-aligned parallel texts for a language pair of your choice (Do make sure that the language you have chosen under 1) is one of the languages in the pair).  The parallel texts and their word alignment files can be found on the Opus website (<http://opus.nlpl.eu>). I would advise you to work with the EuroParl corpus, but if the language you would like to work with is not available, you can check the multiUN and the DGT corpus.  The word alignment files are hidden but can be found using the following example link: <http://opus.nlpl.eu/download/Europarl/en-sv/model/aligned.intersect.gz> This alignment file is for the language pair English-Swedish (en-sv), but you can select an alignment file of any language pair of your choice, provided that the language you chose for the monolingual corpus is among them. We choose the intersection as alignment heuristics, because it is most precise.


<a id="org1845128"></a>

# 4

Building a coocurrence matrix from a corpus:
There are several ways to build a coocurrence matrix depending on the target words you are
selecting (parameter 1) and the type of features, more in particular, the type of context you
are selecting (parameter 2). Please refer back to the slides of the lecture on DSMs for a
list of parameters and a description of the options.
TARGET WORDS:


<a id="org6abc42f"></a>

## 3

Does the monolingual corpus you are using to extract the cooccurrence counts
from provide lemmas? Discuss why using lemmas instead of words often leads to
better performances in DSMs. (3 points)


<a id="org7e1e125"></a>

## 4

Extra points: The parallel text does not provide lemma information, nor PoS tags.
Run a PoS tagger on (both sides of) the parallel text and use the information it
gives you for the DSM. (+5 points)

The data provided with DISSECT already selected target words for you. For the parallel text, and in case you selected your own monolingual text, we take the 1550 most frequent content words (lemmas) in the corpus as target words. In order to determine the 1550 most frequent content words in either corpus, you will need to count all content words. (If you do not have access to PoS information, use a list of stopwords that you filter out.) You then need to rank these words according to their frequency and take the top 1550.


<a id="orgde0e6e8"></a>

## 5

Explain why PoS information can be useful for distinguishing between ambiguous terms. Give some examples from the data you are using. (3 points)


<a id="org187bb8a"></a>

# 6

Please discuss in your report, the different types of features, more in particular, the types of context (parameter 2) that are employed for DSMs in general. (5 points)


<a id="org08a3c4c"></a>

# 7

Discuss what influence the size of the window has on the nature of the semantic relations we find between target word and semantically similar words proposed by the system. What consequences do you think a larger window size would have on the semantically similar words proposed by the system? (3 points)


<a id="org5483908"></a>

# 8

Discuss the differences in output of the DSM (in terms of the similar words it will produce) you expect between the two types of input you are using (the monolingual corpus and the aligned parallel files). Which type of data do you think will generate the highest percentage of synonyms amongst the nearest neighbours? (3 points)


<a id="org1025195"></a>

# 9

Write a python program that extracts coocurrence counts for all target words and features from the parallel aligned files (and the monolingual corpus, if you are using a different corpus than the one provided by DISSECT). Include the extraction program you wrote in the submission, and paste 20 lines (for 20 target words) of the coocurrence counts you extracted in the report. The output of your program should be formatted according to the input format the DSM tool you are using requires. (36 points)


<a id="orgc86dc04"></a>

# 10

Explain what function the feature weighting scheme has. What would be the drawback of doing without a weighting scheme and using raw frequencies instead? (3 points)


<a id="orgca04f0e"></a>

# 11

List the weighting schemes the tool you are using includes and what similarity functions. Make your choice for the weighting scheme and similarity function you will use and motivate your choice in the report. (3 points)


<a id="org021dc0d"></a>

# 12

For both types of corpora (multilingual and monolingual), retrieve the top-5 semantically similar words for five high-frequency words and five low-frequency words from the 1550 words. Paste the output in the report. Is there a difference in the quality of the output for the high-frequency versus the low-frequency words?  Is there a difference for the two types of contexts used? Can you explain what you see? (5 points)


<a id="org4eaf3c5"></a>

# 13

Explain the notion of contextual variability. Take a polysemous word of your choice that is among the 1550 head words you selected. Generate the top-10 semantically similar words for this target word using the monolingual DSM you created. Paste the output in the report. Do you see some consequences of contextual variability in the outputs for this word? Now take the multilingual DSM. Find a polysemous word in the features of the multilingual DSM 1 . For its translation in your target language, find the top-

1.  What are your observations? Do you think using multiple languages

could have improved the multilingual DSM? (5 points)


<a id="orgf1b634c"></a>

# 14

Explain the principle of compositionality and discuss a couple of different ways in which DSMs have been adapted to cater for compositionality. (3 points)


<a id="orgec0b42d"></a>

# 15

Now, let us experiment with compositionality in the monolingual DSM you have just built. Follow the instructions on <http://clic.cimec.unitn.it/composes/toolkit/composing.html> and select a model of your choice (motivate your choice). Show some example output of the composed DSM. Analyse the results. (5 points)


<a id="orgeba726e"></a>

# 16

Is it possible to create a compositional model for the multilingual DSM with the models you have chosen? If so, show some example output here as well.  Analyse the results. (5 points)


<a id="orgbc526bf"></a>

# 17

Discuss the basic tenet of the Prototype Theory in lexical semantics and discuss at least two advantages when compared to the classical theory. (5 points)


<a id="org724666d"></a>

# 18

What are typicality effects? Does the DSM cater for typicality effects? (Hint: You can check the distributional similarity of types of fruit and see if the prototypical examples are more semantically similar to each other than less prototypical examples. You can also check whether prototypical types of fruit have more statistically prominent properties in the coocurrence matrix than less prototypical types of fruit.) (5 points)

