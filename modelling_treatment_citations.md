# Modelling Treatment Citations

## Introduction

An important feature of Taxonomic Treatments -- defined as:

>publications or (more frequently) sections of publications documenting the features or distribution of a related group of organisms (called a “taxon”, plural “taxa”) in ways adhering to highly formalized conventions.[(Catapano, 2010)](#catapano-2010)

are *treatment citations* (in TaxPub, "nomeclature-citations"), described by [(Winston, 1999)](#winston-1999) as

>[citations] of all the names that have been used in published references to [the described] taxon

Therefore, from any treatment, and from treatment to cited treatment, a extensive citation network may be derived revealing the entire history of understanding of a taxon to a given point. This is valuable in many cases, such as when work in one domain (say environmental policy) is based on a taxon name which have been superseded as the accepted name.

As significant citeable entities, treatments and their citations would benefit from more precise modeling to enable more effective use of the information latent in their content and among their relations.

## Conceptual/Ontological Models of treatments

### Treatment notes in Plazi

* [Treatment](https://github.com/plazi/Plazi-Communications/wiki/Treatment), including many links to previous works done in Plazi
* ongoing manuscripts [Treatments](https://docs.google.com/document/d/1cJ1NhH2mMcOvmD8V2ulmi1HpNxn-67ocbSG-LiWmmJ8/edit#heading=h.iqdt6oqetjrp); [Taxonomic treatments in a nutshell](https://docs.google.com/document/d/1sfVskKuBTp5Y67IUQTVZADkUDo8TZIqeM16aKmF13f8/edit?ts=5c66ccd9)

### Treatment data dictionary used in BLR

* [Treatment data dictionary](https://docs.google.com/spreadsheets/d/10uluNbkcu0CfNRog_uOnx_6ytXUSvdH6gx9xltGPqlk/edit#gid=1415791436). See sheet "Final"
* [Treatment feature request](https://docs.google.com/document/d/1X2hDlHJEg8cfZIEChzarfzYU04BPOjxT_qFZI_jFIdQ/edit)

### Treatment tagging in GoldenGate XML

```
<treatment>
     <subSubSection type=nomenclature>
     </subSubSection>
     <subSubSection type=reference_group>
          <treatmentCitationGroup>
               <taxonomicName>
               </taxonomicName>
               <treatmentCitation>
                    <bibRefCitation>
                    </bibRefCitation>
                    <bibRefCitation>
                    </bibRefCitation>
               </treatmentCitation>
               <treatmentCitation>
               </treatmentCitation>
          </treatmentCitationGroup>
          <treatmentCitationGroup>
               <taxonomicName>
               </taxonomicName>
               <treatmentCitation>
               </treatmentCitation>
               <treatmentCitation>
               </treatmentCitation>
          </treatmentCitationGroup>
     </subSubSection type=reference_group>
</treatment>
```
[Example](http://treatment.plazi.org/GgServer/xml/03A10B47FFEBFF93FDB2FBB6FB4DFBF5)

Alternatively, if there is only one reference per taxonomic name, then treatment citation can be tagged as follows:

```
 <subSubSection type=reference_group>
      <treatmentCitation>
           <taxonomicName>
           </taxonomicName>
           <bibRefCitation>
           </bibRefCitation>
      </treatmentCitation>
</subSubSection type=reference_group>
```

Free text can appear in `<treatmentCitation>` or `<treatmentCitationGroup>`, as well as `<materialsCitation>`

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
  * has all relevant properties of frbr:Expression

Treatment Citations are themselves weakly and directly modeled, however. The ontology creates classes for document components based on TaxPub elements including `NomenclatureCitationList` which itself `contains` instances of the class `TaxonomicNameUsage` which itself is extensively modelled to highly granular levels.

### Synospecies/LINDAS/Plazi LOD

[*need to investigate further*]
* Treatments treatTaxonName [TaxonName]
* TaxonName has dwc subproperties
* cite other treatments as articles with part information as subproperties
* effective, but fairly blunt and may be confusing outside of closed system

example: http://treatment.plazi.org/GgServer/lodRdf/03EB87D6144AFFBAFF19703B1B5EF9A7

## Proposals

* following OpenBiodiv-O
  * Treatments are frbr:Expressions or something similar realizing Taxon Concepts
  * as frbr:expression has properties of relevant bibliographic ontologies (esp SPAR, FaBIO, DOCO)
* following Treatment Ontology
  * Treatments cito:cite and are cito:citedBy other Treatments
* Following both Taxon or TaxonConcepts have relevant DWC subproperties
* perhaps Treatments are instances of or a subclass of TaxonomicNameUsage
* extend cito:cites subclass to address specific citings done among treatments e.g., synonymization
* adopt generally useful pragmatic features of Plazi LOD

## Revised TaxPub model

### Review
* existing model works, if too restrictive
* must be sufficient to convert programmatically to minimum required formal LOD expression

### Proposals
  * rename "nomenclature-citation" "treatment-citation"
  * loosen restrictions on where available
  * use mixed-content model
  * attributes to refine semantics of citation



## References
* <span href="#catapano-2010">Catapano T. TaxPub: An Extension of the NLM/NCBI Journal Publishing DTD for Taxonomic Descriptions. In: Journal Article Tag Suite Conference (JATS-Con) Proceedings 2010 [Internet]. Bethesda (MD): National Center for Biotechnology Information (US); 2010. Available from: https://www.ncbi.nlm.nih.gov/books/NBK47081/ </span>

* <span href="#morris-catapano-2016">Morris, R & Catapano, T. Treatment Ontology. 2016 Available from https://github.com/plazi/TreatmentOntologies) </span>

* <span href="#senderov-2018">Senderov, Viktor, Kiril Simov, Nico Franz, Pavel Stoev, Terry Catapano, Donat Agosti, Guido Sautter, Robert A. Morris, and Lyubomir Penev. “OpenBiodiv-O: Ontology of the OpenBiodiv Knowledge Management System.” Journal of Biomedical Semantics 9, no. 1 (January 18, 2018): 5. https://doi.org/10.1186/s13326-017-0174-5.
</span>

* <span href="#Winston-1999">Winston J. Describing Species. New York: Columbia University Press; 1999. p. 136</span> available here https://drive.google.com/open?id=1Xfnhq4oAwId_S96rXZYgyDCE1knhVV3o.
