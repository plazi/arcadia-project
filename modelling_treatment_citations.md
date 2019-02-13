# Modelling Treatment Citations

## Introduction

An important feature of Taxonomic Treatments -- defined as:

>publications or (more frequently) sections of publications documenting the features or distribution of a related group of organisms (called a “taxon”, plural “taxa”) in ways adhering to highly formalized conventions.[(Catapano, 2010)](#catapano-2010)

are *treatment citations* (in TaxPub, "nomeclature-citations"), described by [(Winston, 1999)](#winston-1999) as

>[citations] of all the names that have been used in published references to [the described] taxon

Therefore, from any treatment, and from treatment to cited treatment, a extensive citation network may be derived the entire history of understanding of a taxon to a given point. This is valuable in many cases, such as when work in one domain (say environmental policy) is based on a taxon name which have been superseded as the accepted name.

As significant citeable entities, treatments and their citations would benefit from more precise modeling to enable more effective use of the information latent in their content and among their relations.

## Conceptual/Ontological Models of treatments

### Treament Ontology
([Morris and Catapano, 2016](#morris-catapano-2016))

* OWL ontology
* tmt:treatment, with properties
 * tmt:definesTaxonConcept A
 * tmt:publishedIn B
 * cito:cites C

   * where

     * A is a dwcFP:Taxon (Darwin Core Filtered Push) with Darwin Core properties
     * B is the source publication with properties from an appropriate ontology (e.g., BIBO, FaBIO, etc...)
     * C is a tmt:treatment

* cito:cites could be refined by any of its subproperties see http://purl.org/spar/cito/cites

* did not well model the properties of the publication component corresponding to the treatment (e.g, page range), for this DOCO could be used

### OpenBiodiv-O
([Senderov, V et al 2018](#senderov-2018))

* Utilizes Concept Taxonomy framework
* TaxonConcept
 * is a subclass of both frbr:Work and a skos:Concept
 * Treatment is equivalent class to dwc:Taxon
* TaxonConcept as frbr:Work:
 * has frbr:realization Treatment
 * Treatment is a frbr:Expression

## References
<span href="#catapano-2010">Catapano T. TaxPub: An Extension of the NLM/NCBI Journal Publishing DTD for Taxonomic Descriptions. In: Journal Article Tag Suite Conference (JATS-Con) Proceedings 2010 [Internet]. Bethesda (MD): National Center for Biotechnology Information (US); 2010. Available from: https://www.ncbi.nlm.nih.gov/books/NBK47081/ </span>

<span href="#morris-catapano-2016">Morris, R & Catapano, T. Treatment Ontology. 2016 Available from https://github.com/plazi/TreatmentOntologies) </span>

<span href="#senderov-2018">Senderov, Viktor, Kiril Simov, Nico Franz, Pavel Stoev, Terry Catapano, Donat Agosti, Guido Sautter, Robert A. Morris, and Lyubomir Penev. “OpenBiodiv-O: Ontology of the OpenBiodiv Knowledge Management System.” Journal of Biomedical Semantics 9, no. 1 (January 18, 2018): 5. https://doi.org/10.1186/s13326-017-0174-5.
</span>

<span href="#Winston-1999">Winston J. Describing Species. New York: Columbia University Press; 1999. p. 136</span>
