
# Getty Art and Architecture Thesaurus


## Landscape Analysis of the Getty AAT

### Setup
If you want to be able to execute the code in this repository, please take note of the following: 
- This notebook is written with the assumption that you run it in [Visual Studio Code](https://code.visualstudio.com/), with the following extensions: Python, SPARQL Executor, and REST Client. Some functionality may otherwise not be available.
- Please install the packages that are specified in `requirements.txt`(requirements.txt). 

### Analysis Structure 
- [`gettyOverview.ipynb`](gettyOverview.ipynb) contains an overview of the following of the main conceptual and technical aspects of Getty AAT and ULAN
- [`AAT_concepts.ipynb`](AAT_concepts.ipynb) delves into the semantic anatomy of a AAT concept; And explain how AAT hierarchies are created.
- `resources.md`(resources.md) provides a list of the documentation that was consulted in the process of creating the landscape analysis. 


## Art and Architecture Thesaurus Concepts (AATC) Controlled Vocabulary

The Art and Architecture Thesaurus Concepts (AATC) is a *slim*, or a subsection of Getty AAT concepts. 

In more technical terms, the AATC is a SKOS concept scheme that restructures the concepts from the Art and Architecture Thesaurus (AAT) into a flat controlled vocabulary, and excludes non-concepts, such as facets, hierarchies and guide terms. 
The result is a controlled vocabulary where each term is a `skos:Concept`, member of `aatc: skos:ConceptScheme`, with English(@en) and Dutch(@nl) labels. 

Original URI are kept, and users are encourage to find more information and reference the term through its URI. 

Result: [aatc.ttl](aatc.ttl) 

### Motivation 

AATC development was motivated by the need to index AAT terms in a Skosmos server, so that AAT terms could be used easily queried via the Skosmos API and easily used by software applications to classify data with AAT terms.

Since our current use-cases, that called for the us of AAT concepts, were not concerned with ancestry of the concepts, we have decided to no preserve the  hierarchical relations of AAT. Instead, we focused on creating a flat controlled vocabulary, containing all concepts that included both English and Dutch labels.

### AATC Creation

[aatc_generation.ipynb](aatc_generation.ipynb)

AATC was created via a `CONSTRUCT` SPARQL query in [aatc_generation.ipynb](aatc_generation.ipynb) that transforms the query result onto a new structure, saved in the RDF based turtle (.ttl) format and can be seen in [aatc.ttl](aatc.ttl) (~8Mb) 


### AATC Indexing in Skosmos

TODO
* namespace aatc: https://vocabularies.dans.knaw.nl/aatconcepts
* homepage:  https://vocabs.datastations.nl/aatconcepts



# Important Links or *How to find your way around in the Getty Maze*

* [Vocabularies Downloads](https://www.getty.edu/research/tools/vocabularies/obtain/download.html)
* [AAT Hierarchy](https://www.getty.edu/vow/AATHierarchy?find=&logic=AND&note=&english=N&subjectid=300000000)
* [Technical Vocabularies Documentation](http://vocab.getty.edu/doc/)
* [SPARQL UI](https://vocab.getty.edu/queries#Finding_Subjects)
* [Semantic view](https://vocab.getty.edu/aat/) (Top of hierarchy)
* [ODC-By license](https://opendatacommons.org/licenses/by/1-0/)


# TODOs
* issue: attc.ttl URI becomes http and does not use the prefix
* index AATC in Skosmos and see what changes might be need to perform to aatc structure
* rename repo landscape-analysis-Getty-AAT -> Getty-AAT
* move repo to DANS-labs org