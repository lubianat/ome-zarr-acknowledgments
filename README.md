# OME-Zarr Acknowledgments

This repository keeps a curated list of people, affiliations, and resources tied to the OME-Zarr/OME-NGFF ecosystem, and serves the acknowledgments page published from this data.

## How it works

| File                                                       | Purpose                                                                                                         |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [`people.yaml`](people.yaml)                               | Holds the canonical list of people, their affiliations, optional ORCIDs, and the resources that reference them. |
| [`affiliation_shortener.yaml`](affiliation_shortener.yaml) | Maps long-form affiliations to short labels, country codes, and optional ordering preferences.                  |
| [`index.html`](index.html)                                 | Loads the YAML files in the browser and renders the public acknowledgments view.                                |

Anyone with at least one affiliation and a `resource` other than the image.sc forum appears in the highlighted contributors section near the top of the page.

## Add a missing name

### Let us know

Contact [Tiago](https://tiago.bio.br) or open an [issue](https://github.com/german-BioImaging/ome-zarr-acknowledgements/issues/new?template=add-contributor.yml) if you prefer not to edit the files yourself.

### Open a pull request yourself

1. Fork this repository.
2. Add or extend a `resource` entry in [`people.yaml`](people.yaml). For example:

    ```
        name: RFC-6 people
        url: https://ngff.openmicroscopy.org/rfc/6/index.html
        people:
          - Norman Rzepka
    ```

   You can also append the person to the `others` resource if that is more appropriate.
3. Ensure the person also appears in the top-level `people` list with at least one affiliation and (optionally) an ORCID.
4. Confirm the referenced affiliation appears in [`affiliation_shortener.yaml`](affiliation_shortener.yaml) with a `short_name`. Add or update the entry if needed.
5. Open a pull request describing the change.

## Modify existing information

1. Edit the relevant entry in [`people.yaml`](people.yaml); every person listed there should keep at least one affiliation and, if possible, an ORCID.
2. Update [`affiliation_shortener.yaml`](affiliation_shortener.yaml) whenever you rename, add, or remove affiliations so the short names and countries stay in sync.
3. If you change data that affects how the site renders, preview [`index.html`](index.html) locally (e.g., via a simple HTTP server) to confirm the layout still looks right.

## Control the order within an affiliation

Use the optional `order_override` parameter inside [`affiliation_shortener.yaml`](affiliation_shortener.yaml) to pin the display order for members of a specific affiliation. For example:

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

## Seed new data

- Use an LLM to extract affiliations and format YAML directly from PDF author lists.
- Call the CrossRef API (for example https://api.crossref.org/works/10.1038/s41592-021-01326-w) to enrich the metadata.
- Copy subscribers from https://imagesc.zulipchat.com/#narrow/channel/328251-NGFF into an LLM prompt for fast formatting.
- Shorten new affiliations by adding entries to [`affiliation_shortener.yaml`](affiliation_shortener.yaml).

## Updates

Direct pull requests that update [`people.yaml`](people.yaml) or [`affiliation_shortener.yaml`](affiliation_shortener.yaml) are always welcome.