# annostore Workflow

* [POA 2024 Annostor workshop papers](https://docs.google.com/spreadsheets/d/1EasdU-yhV_bI_g6weEIcuJLdCUvgkxpTXKzmSt82vAY/edit?gid=0#gid=0)
* [Annostore activities at POA](https://arcadia2.annostor.org/activities)

## Activities

## Metadata
In this workflow (Accession), the `title, authors, abstract, keywords, PIDs (DOI, ISSN, etc.), journal, publication date (year), and copyrights` are added. 

The OCR is captured normally, and we only need to edit typographical errors or accents.

## Treatments
In this workflow (Treatments), treatments and subSubSections are added, the latter being divided into nomenclature and multiple. 
The continuation of a treatment or subSubSection is indicated by the repetition of the same treatment or subSubSection number in the annotations made on the following pages.   

There is no OCR capture.

`<treatments>`   
`<subSubSection>`   

[Example](https://zenodo.org/records/12605625)
![image](https://github.com/plazi/arcadia-project/assets/4609956/e6de52da-742a-4b1d-b6ac-b6fe0baf1fc1)


## Taxonomic names
In this workflow (still under Treatments), the taxonomic names of the target taxa of each treatment are added. 
The annotation of the taxonomic name is included within a nomenclature subSubSection annotation. 
The OCR is captured but not recognized, so all taxonomic names must be included manually.

`<taxonomicName>`   

[Example](https://zenodo.org/records/12605625)
![image](https://github.com/plazi/arcadia-project/assets/4609956/c1abc527-83af-4a04-ad27-21084393e6d2)


## Material citations
There is no workflow ready yet
