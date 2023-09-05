# GMDS 2023: Terminologieserver (TS) - Challenge
This repository contains the resources for the GMDS 2023 terminology server challenge. 

The aim of the TS-Challenge is to present different terminology servers and their functionalities to the audience under comparable conditions. The participating vendors demonstrate which terminology interactions are possible on their product via the FHIR RESTful API and FHIR terminology module. A standardized set of tasks is provided on the basis of predefined API requests organized within a Postman Collection.

## Information about the workshop
https://mii-termserv.de/en/blogs/2023-07-17-gmds-terminology-server-challenge/


## Prerequisites
The collection consists of several folders for the individual operations. The needed CodeSystems, ValueSets and ConceptMaps can be found in the '02 Resources' folder. For each resource exists a PUT request containing the relevant data in the body. The server endpoint and MIME-types can be configured through the collection variables.

Additional required CodeSystems:
- SNOMED CT [Version: January 2021](https://download.nlm.nih.gov/umls/kss/IHTSDO20210131/SnomedCT_InternationalRF2_PRODUCTION_20210131T120000Z.zip?_gl=1*otxhn2*_ga*NjQ3NDE2NDMwLjE2OTExNTEwNTc.*_ga_P1FPTH9PL4*MTY5MTE1MTA1Ny4xLjEuMTY5MTE1MTE5Ni4wLjAuMA..*_ga_7147EPK006*MTY5MTE1MTA1Ny4xLjEuMTY5MTE1MTE5Ni4wLjAuMA..) 

For importing the collection in Postman see: [Importing data into Postman](https://learning.postman.com/docs/getting-started/importing-and-exporting/importing-and-exporting-overview/)

## User stories
Introduction:
In a Molecular Tumor Board (MTB), an interdisciplinary team of physicians creates therapy recommendations for patients with oncological diseases beyond standard treatment options. In a MTB, the software cBioPortal shall be used to visualize molecular genetics and clinical data and to support decision-making. cBioPortal uses OncoTree, a hierarchically organized structure for the classification of currently 868 tumor types. By considering a tumor’s histology and localization, it can be matched to a node of the OncoTree. In pathology reports, neoplasms are routinely coded using the ICD-O classification. ICD-O differentiates between codes of two axes – topography and morphology – which are combined into a tuple. In addition to the ICD-O and OncoTree coding systems, the terminology SNOMED CT will also be used.

1. I want to load the terminologies used by the project (like ICD-O-3, OncoTree and SNOMED CT).
2. Several codes from different coding systems [SNOMED CT, ICD-O-3, OncoTree] are available. It should be checked whether the individual codes are allowed in the associated CodeSystems and ValueSets.
3. The correct [SNOMED CT, ICD-O-3] codes should be looked up to obtain additional information, such as the display name.
4. I want to test the subsumption relationship between two SNOMED CT codes.
5. I want to translate a ICD-O-3 code to SNOMED CT based on a provided mapping.
6. I want support from the terminological service for maintaining a transitive closure table.

## Changelog

### Update on 2023-09-05

A number of inconsistencies and other oversights were fixed:

- The canonical URL of the ICD-O-3 CodeSystem resource was corrected as to make it consistent with the rest of the collection; also fixed the ID for PUT operation.
- The ConceptMap for ICD-O-3 tuples to OncoTree contained in the collection was not the correct resource. Updated the contained resource.
- A number of test scripts were broken for the tests where a non-result was expected. This was due to incorrect escapes for `"` characters, this was fixed where broken and preemptively corrected for those tests where this issue might also occur.
- The closure example was corrected to take the version of the ICD-O resource correctly into account.
- A few typos were fixed.
