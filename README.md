# GMDS 2023: Terminologieserver (TS) - Challenge
This repository contains the resources for the GMDS 2023 terminology server challenge. 

The collection consists of several folders for the individual operations. The needed CodeSystems, ValueSets and ConceptMaps can be found in the '02 Resources' folder. For each resource exists a PUT request containing the relevant data in the body. The server endpoint can be configured through the environment (url variable).

Additional required CodeSystems:
- SNOMED CT
- LOINC

For importing the collection and environment in Postman see: [Importing data into Postman](https://learning.postman.com/docs/getting-started/importing-and-exporting/importing-and-exporting-overview/)

# User stories
Introduction:
In a Molecular Tumor Board (MTB), an interdisciplinary team of physicians creates therapy recommendations for patients with oncological diseases beyond standard treatment options. In a MTB, the software cBioPortal shall be used to visualize molecular genetics and clinical data and to support decision-making. cBioPortal uses OncoTree, a hierarchically organized structure for the classification of currently 868 tumor types. By considering a tumor’s histology and localization, it can be matched to a node of the OncoTree. In pathology reports, neoplasms are routinely coded using the ICD-O classification. ICD-O differentiates between codes of two axes – topography and morphology – which are combined into a tuple. In addition to the ICD-O and OncoTree coding systems, the terminology SNOMED CT will also be used.

1. I want to load the terminologies used by the project (like ICD-O-3, OncoTree and SNOMED CT).
2. Several codes from different coding systems [SNOMED CT, ICD-O-3, OncoTree] are available. It should be checked whether the individual codes are allowed in the associated CodeSystems and ValueSets.
3. The correct [SNOMED CT, ICD-O-3, LOINC] codes should be looked up to obtain additional information, such as the display name.
4. I want to test the subsumption relationship between two SNOMED CT codes.
5. I want to translate a ICD-O-3 code to SNOMED CT based on a provided mapping.
6. I want support from the terminological service for maintaining a transitive closure table.
