# EAMENA Quick Pin

**Location-first data entry for Arches heritage databases.**

EAMENA Quick Pin is an [Arches](https://www.archesproject.org/) plugin developed for the
[Endangered Archaeology in the Middle East and North Africa (EAMENA)](https://database.eamena.org)
database at the University of Oxford. 

EAMENA database URL: database.eamena.org
EAMENA Project website: eamena.org

In the standard Arches workflow, recording is form-first: a site is located in external
software such as Google Earth, its coordinates are converted to GeoJSON, and the geometry
is then entered into the record. Quick Pin reverses this order:

1. Find the site on the map
2. Place a **point** or draw a **polygon**
3. Save it as a new **Heritage Place**
4. Open the record and add the remaining data

## Features

- Existing heritage places displayed on the map to help avoid duplicates
- Search by longitude/latitude or pasted GeoJSON
- Editable polygon vertices before saving
- Creates the Heritage Place record directly through the Arches tile API

## Installation

Copy the files into your Arches project, keeping the same folder structure:

    <project>/plugins/eamena-quick-pin.json
    <project>/media/js/views/components/plugins/eamena-quick-pin.js
    <project>/templates/views/components/plugins/eamena-quick-pin.htm

Register the plugin and rebuild the front end:

    python manage.py plugin register --source <project>/plugins/eamena-quick-pin.json
    npm run build_production
    python manage.py collectstatic --noinput

The resource model and node IDs in `eamena-quick-pin.js` are set for the EAMENA
Heritage Place model and must be changed for other Arches projects.

## Use in EAMENA

Quick Pin is deployed on the EAMENA database. Its integration into the EAMENA codebase
is in [eamena-project/eamena#7](https://github.com/eamena-project/eamena/pull/7).

## Citation

Please cite this software using the metadata in `CITATION.cff`
(GitHub's "Cite this repository" button) or its Zenodo DOI.

## Licence

GNU General Public License v3.0
