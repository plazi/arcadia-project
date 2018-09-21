## **Taxonomic treatment processing**

**Taxonomic treatment** - quality checking will be automated (\*) and
possible errors will be flagged and communicated to the QA/QC team

Article metadata \*

Treatment boundaries \*

> Nomenclature section \*
> 
> Taxonomic name \*
> 
> Taxonomic name label (taxonomic status label) \*

Subsubsection type=diagnosis/description \*

Conditional: if nomenclature status n.sp. Then there must be a

> Material citation string delimited \*
> 
> Holotype type status \*
> 
> Collection code \*

Taxonomic Treatment

Definition: A Taxonomic Treatment is a subarticle element scientists
publish to include data about a specific taxon. They are required by the
Codes to describe new species/taxa. They include data that define
synonymies of taxa (e.g. deprecations of names; links to synonymized
taxon: treatmentCitations) or augment the knowledge about the respective
taxon, or materialsciations of specimens used in the study leading to
the taxonomic treatment, including the required materials citation of
the holotype designation for a new species. Tens of millions of
Treatments have been published. Annually 17,000 treatments are published
to describe new species for science and an estimated 130,000 that
augment or deprecate existing taxa.

Structure: Text that begins in most cases with a nomenclature subsub
section, followed by one or several other subsub section elements. that
includes a taxonomic name and ends with an other structurally clearly
separated new subsection in the text that can be another treatment,
general discussion.

Why is it important: All the data in a treatment are related to the
taxon defined in the nomenclature subsubsection and allow to make
unambigous statement about this species that the scientists implicitly
makes by publishing taxonomic treatments Taxonomic treatments are data
and thus can be reused even if they have been published in a closed
access article. They can be extracted by machine and are increasingly
published used the semantic element “taxonomic-treatment” defined in
JATS/Taxpub.

User case: A user wants to know how many treatments have been published
based on material from his collection (collection code). He submits a
query using his collection code. He gets either a number of taxonomic
treatments or a list of all the taxonomic treatments.

**Nomenclature SubSubSection**

Nomenclature SubSubsection boundary

Inclusion of a taxonomic name

Inclusion of a taxonomic status label

Nomenclature SubSubsection

Definition:.

Why is it important:.

User case:.

Taxonomic status label

Definition: Defines whether the taxonomic treatment is about a new
species (nov.spec), the name has be changed (nov. comb) or has been
deprecated (synonymized; nov. syn.). A taxonomic status label is
required by the Codes for new species and objective synonym (issues
regulated by the codes such as resolution of the usage of the same name
(e.g. homonymy) or suggested in the case of subjective synonymy, a
scientific decision to synonymize to taxa which results in the
deprecation of the younger taxon.

Why is it important: Taxonomic status labels are explicitly used by
scientists to indicate nomenclatural acts or changes in the names of
taxa. Only they allow to unambiguously know whether a taxon is a new
taxon. The terms new species might occur anywhere in the text and not
necessarily diagnose the the treatment is about a new species.

User case: Give me a list of the new species. The user submits a query
requiring the number of new species. The user will get a list of all the
new species.

**TreatmentCitation?**

If taxonomic status label = new taxon, then a treatment citation is not
supposed to be there

If taxonomic status label = NOT a new taxon, then a treatment citation
should/supposed to be there

NEED A HUMAN CHECKING FOR EACH INDIVIDUAL TREATMENT CITATION -
concluding that if QC/QA could not be automated we do not do that by
human power (but treatment citations will be marked up by all means)

TreatmentCitation

Definition:.

Why is it important:.

User case:.

**Figure citations** in the entire treatment

How this will be automated and what has to be checked

If there is a figure citation in the treatment, it has to have caption
plus Zenodo DOI - should be easily automated

Figure citation

Definition:.

Why is it important:.

User case:.

**Bibliographic in-text citations** (in the treatment) **and references
**

Similar procedure as for figures

The tool marks up:

> Bibliographic citation in the treatment
> 
> Is there a corresponding reference in the reference list of the
> article

To check: when there is a bibliographic citation in the treatment but no
corresponding reference in the reference list, then check if the
reference is missing or not just marked up.

Bibliographic in-text citation

Definition:.

Why is it important:.

User case:.

Bibliographic reference

Definition:.

Why is it important:.

User case:.

**Taxonomic names**

Verbatim name string marked in a taxonomicName tag

Normalization?

Scope?

All names in the treatment / nomenclature section / treatment citations?

What the automated check is expected to do?

What humans are expected to check, after automated checking reports a
possible error?

  - > For all marked up taxon names if they are delimited correctly

  - > Checking accuracy of the parsing

  - > Is the taxon in the right higher category

Taxonomic name

Definition:.

Why is it important:.

User case:.

**Definitions**

Code. Taxonomic names are regulated by Codes. The are specific for
zoology, botany, mycology, micro organisms….

SubSection: A SubSection of an article. Each SubSection of an article is
of a particular type, e.g. Introduction, results, abstract,
bibliographic reference, taxonomic treatment

SubSubSection: A section of a taxonomic treatment. Each SubSubSection is
a particular type, e.g. nomenclature, diagnosis, description,
materialsCitation

**Notes**

To what granularity do we markup?

Do tests to see feasibility by both Plazi and Pensoft

Design a dashboard that includes all the elements above

Include a link from the dashboard to the respective flagged element

Once an issue is resolved, take it out from the dashboard

**Next Steps:**

  - > Draft of criteria stated above

  - > Define automated rule checking logic to flag possible errors

  - > Define new QA related interface features
    
      - > Include a link from the dashboard to the respective flagged
        > element
    
      - > Once an issue is resolved, take it out from the dashboard
    
      - > Others

  - > Test run of QA process, iteratively revise/refine process and
    > propose new features

  - > Reevaluate estimate of total \# of treatments to be processed

  - > Plan for implementation
