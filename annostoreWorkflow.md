# annostor Workflow

* [POA 2024 Annostor workshop papers](https://docs.google.com/spreadsheets/d/1EasdU-yhV_bI_g6weEIcuJLdCUvgkxpTXKzmSt82vAY/edit?gid=0#gid=0)
* [Annostore activities at POA](https://arcadia2.annostor.org/activities)

## Activities

## Annotation process
Using the Annostor tool, to create a new annotation we first need to position the entire text to be marked within the field of view. Next, we click on "create new annotation" (plus sign icon at the top of the left sidebar) and select the entire area to be marked with the box that appears. In the sidebar that opens on the right side of the page, we select the "annotation type," whether it belongs to a "group," and click "save". The annotations made will be listed in the sidebar on the left side of the page. 

For the "group" option, if the beginning of the annotation in question has already been marked on another page or different column of text, we select the same numbering designated for that section. For example, if treatment2 continues on the next page, the annotation for the subsequent `treatment` should also be marked as treatment2, using the selection available in the "group" option. If the marking is wrong and an annotation needs to be deleted, we can do so by clicking on the trash icon that appears in the upper right corner of the annotation.

Annotations for `subSubSections` need to be made entirely within their respective `treatments`, and `taxonomic names` need to be included within `nomenclature subSubSections`. If they extend beyond these areas, the annotation will be considered invalid.  When an annotation is included within another, this indication of belonging is noted in the sidebar of annotations, just below the name of the annotation itself, using "in". Example:
`taxonomicName1`
`- in nomenclature1`

We can edit the annotations by clicking on the pencil icon that also appears in the upper right corner of the annotation. Additionally, if it is a type of annotation that detects OCR, we can correct it in the text box presented under "notes." Note that for OCR editing, the annotation needs to have been saved at least once before editing, otherwise the modification will not be saved.

After adding all the annotations to the document, we click on "Mark for review", just above the tab where the list of annotations is located, next to "create new annotation."

![image](https://github.com/plazi/arcadia-project/assets/92064978/48655228-e029-4ca0-90bb-d26f7f3db6a0)

## Accession workflow: Metadata
In this workflow (Accession), the `title`, `authors`, `abstract`, `keywords`, `PIDs` (`DOI`, `ISSN`, etc.), `journal`, `publication date` (`year`), and `copyrights` are added. 

The OCR is captured normally, and we only need to edit typographical errors or accents.

## Taxonomic treatments workflow
In this workflow (Treatments), treatments and subSubSections are added, the latter being divided into nomenclature and multiple. 
The continuation of a treatment or subSubSection is indicated by the repetition of the same treatment or subSubSection number in the annotations made on the following pages. SubSubSection can be attributed with `nomenclature section` or `multiple section` 

There is no OCR capture.

`<treatments>`   
`<subSubSection>`:
    `nomenclature section` or `multiple section` 

[Example](https://zenodo.org/records/12605625)
![image](https://github.com/plazi/arcadia-project/assets/4609956/e6de52da-742a-4b1d-b6ac-b6fe0baf1fc1)


## Taxonomic name workflow
In this workflow (still under Treatments), the taxonomic names of the target taxa of each treatment are added. 
The annotation of the taxonomic name is included within a nomenclature subSubSection annotation. 
The OCR is captured but not recognized, so all taxonomic names must be included manually.

`<taxonomicName>`   

[Example](https://zenodo.org/records/12605625)
![image](https://github.com/plazi/arcadia-project/assets/4609956/c1abc527-83af-4a04-ad27-21084393e6d2)


## Material citations
There is no workflow ready yet
