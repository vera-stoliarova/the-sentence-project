# the-sentence-project
### Vocabulary exercise generator for language learning based on the corpus of teenage fiction and TV series scripts

As an English Language instructor, while teaching or recycling/revising vocabulary I have often encountered a situation when:

* there were not enough practice exercises on target language in the chosen coursebook;
* the exercises were linked by a single topic and failed to demonstrate the variety of context a vocabulary unit could be used in;
* I wanted to draw my students’ attention to and practise extra vocabulary units instead of or in addition to those picked by the authors of the chosen coursebook;
* I wanted to build up my students’ motivation to study by demonstrating how target vocabulary was used outside the coursebook in their favourite books and films thus encouraging them to read/watch more in English rather than with translation. 

In my experience, **a gap-fill exercise** is one of the best ways not only to practice meaning and form, but also teach students to notice collocates and co-text. However, creating such exercises by looking up examples in dictionaries or books could be a time-consuming an tedious task because you can only look up one item at a time, you have to copy/paste the sentence and edit it.

That is how I came up with an idea to write a program that could make **vocabulary exercise generation** easier.

At the current stage, the program takes a book as a corpus (the program can potentially be used to extract examples from film or TV series scripts) and searches the sentences for target vocabulary units. The program outputs the sentences ordered by unit in two variants: with the target unit capitalised (for the teacher’s convenience) followed by a gapped sentence. 

The main advantage of the program is that you can look for **a few vocabulary units at a time**.

Of course, the output requires some further editing by the teacher, but it is still not as much as it normally takes.

Below is an example of the use of the exercise generator based on Harry Potter series.

The first piece of code extracts text from xml books, joins the books together and writes them into one text file using lxml.

* [XML extractor](https://github.com/vera-stoliarova/the-sentence-project/blob/master/harry_potter_xml_full_corpus.ipynb)

Then the sentences in the text are separated from each other. 

The two functions - extract_sentence_word and extract_sentence_phrase, - are introduced for different types of input.

**extract_sentence_word** looks for individual words or inseparable phrasal verbs or phrases. The functions searches through the sentences using a simple for-loop. At the moment the code is not able to track word forms, so the user has to put them in him/herself. 

**extract_sentence_phrase** can be used to find two-part separable phrases such as phrasal verbs of verb-noun word-combinations using regular expressions.

In both cases the search is case-insensitive.

* [Sentence extractor](https://github.com/vera-stoliarova/the-sentence-project/blob/master/sentence_project_v.2.ipynb)
