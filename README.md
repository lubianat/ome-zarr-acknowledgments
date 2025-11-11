
# How does it work


People related to the development of OME-Zarr/OME-NGFF are listed with affiliations in `people.yaml`. A shortener for big affiliations is available on `affiliation_shortener`, which also maps affiliations to countries.

Info from the yaml files is pulled and displayed by index.html.

Any people with at least 1 affiliation and linked to some `resource` other than the image.sc forum are shown in the upper part. 

## Adding a missing name

### Let us know 

Let [https://tiago.bio.br](Tiago) know or, if confortable, open an issue on the issue tracker

### Add it directly

– Fork the repository 

— Add a "resource" containing the person name to people.yaml, e.g. 

```
    name: RFC-6 people
    url: https://ngff.openmicroscopy.org/rfc/6/index.html
    people: 
      - Norman Rzepka
```

alternatively, add it to the resource "others" 

— make sure your name is listed in the "people" list, with an affiliation and (optionally) an ORCID

— make sure your affiliation has a short name on `affiliation_shortener.yaml` 

— make a pull request

## Modifying information

— to modify an affiliation or a mention in the upper or lower part, edit `people.yaml` directly 

— make sure your name is listed in the "people" list, with some affiliation and (optionally) an ORCID

— make sure your affiliation has a short name on `affiliation_shortener.yaml` 

## Changing order within an affiliation

Order of names within an affiliation can be overriden if needed on  `affiliation_shortener.yaml` by tweaking the "    order_override:" optional parameter. E.g., for GerBi

```
  - full_name: "German BioImaging-Gesellschaft für Mikroskopie und Bildanalyse e.V., Constance, Germany"
    short_name: "GerBI"
    country_code: "DE"
    order_override:
        - Josh Moore
        - Johannes Soltwedel
        - Tiago Lubiana
        - Janina Hanne
        - Stefanie Weidtkamp-Peters
```


# Seeding 

– Use LLM to extract affiliations + format YML based given a copy-paste of authors on PDFs for papers

– Use the CrossRef API (e.g. https://api.crossref.org/works/10.1038/s41592-021-01326-w) to enrich with extra information

– Copy-paste subscribers from https://imagesc.zulipchat.com/#narrow/channel/328251-NGFF into LLM for formatting

– Manually shorten affiliations with affiliation_shortener.yaml

# Updates

Direct pull-requests changing the information on afilliation_shortner.yaml or people.yaml are welcome! 