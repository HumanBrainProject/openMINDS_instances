# openMINDS_instances

⚠️ ⚠️ **THIS REPOSITORY IS DEPRECATED** ⚠️ ⚠️ 

***Recent changes in the structure of the openMINDS repositories that were made to better handle versioning of the openMINDS schemas led to decision to move all instances to the version branches of the openMINDS metadata model repositories of the respective schemas they are validated against.***

The openMINDS_instances repository is part of the **open** **M**etadata **I**nitiative for **N**euroscience **D**ata **S**tructures (openMINDS). It contains well defined metadata representations (JSON-LDs) that are most likely to be reused across different research products. Currently, openMINDS provides predefined instances for all ControlledTerms, Licence, and ContentType schemas. 

**How to request new instances?** Requests for adding new instances to this libraray can be made by getting in touch with the openMINDS development team (through the Issues or the support email: coming soon). The team will attend to a request as soon as possible. Note that instances should be well defined to be useful for the community. They should at least provide a one sentence definition, and where applicable a reference to a matching ontology term (for ControlledTerms) or another official resource (e.g., IANA for ContentType or SPDX for License). If you would like to contribute, cf. also [CONTRIBUTING](https://github.com/HumanBrainProject/openMINDS_instances/blob/v1/CONTRIBUTING.md).

**How to correctly define an openMINDS instance?** openMINDS instances are written as JSON-LDs. A correctly instantiated openMINDS JSON-LD should always contain the following technical attributes, and at least the required properties of the respective schema type they are validated against:

```json
{
  "@context": {
    "@vocab": "https://openminds.ebrains.eu/vocab/"
  },
  "@type": "OPENMINDS_SCHEMA_TYPE",
  "@id": "https://openminds.ebrains.eu/instances/OPENMINDS_SCHEMA_NAME/HUMAN_READABLE_INSTANCE_ID",
  "PROPERTY_NAME": "METADATA_VALUE"
}
```

The values written in capital letters need to be replaced accordingly. Here a full example of an instance for an openMINDS_controlledTerms schema type (cf. `/instances/species/homoSapiens.jsonld`):

```json
{
  "@context": {
    "@vocab": "https://openminds.ebrains.eu/vocab/"
  },
  "@id": "https://openminds.ebrains.eu/instances/species/homoSapiens",
  "@type": "https://openminds.ebrains.eu/controlledTerms/Species",
  "definition": "The species *Homo sapiens* (humans) belongs to the family of *hominidae* (great apes).",
  "description": null,
  "interlexIdentifier": "http://uri.interlex.org/base/ilx_0105114",
  "knowledgeSpaceLink": "https://knowledge-space.org/wiki/NCBITaxon:9606#human",
  "name": "Homo sapiens",
  "preferredOntologyIdentifier": "http://purl.obolibrary.org/obo/NCBITaxon_9606",
  "synonym": [
    "Homo sapien",
    "human",
    "man"
  ] 
}
```
Note that properties that are defined as optional in an openMINDS schema can either be provided with a `null` value in the JSON-LD or left out completely.

### License

The work on this GitHub repository is licensed under the MIT License.
