# sl2gtfs

Python helpers for converting between SL site ids and Sweden national stop ids.

    pip install sl2gtfs

## Usage

Requires an API key at [Trafiklab](https://www.trafiklab.se/api/gtfs-sverige) for [GTFS Sweden](https://www.trafiklab.se/api/gtfs-sverige) and [SL stops and routes](https://www.trafiklab.se/api/sl-hallplatser-och-linjer-2).

```
Usage: sl2gtfs [options]

Options:
  -h, --help            show this help message and exit
  -s SL_SITE_URL, --sl-site-url=SL_SITE_URL
                        Url for SL sites.
  -g GTFS_STOPS_URL, --gtfs-stops-url=GTFS_STOPS_URL
                        Url for GTFS SL mapping.
  --pygtfs2sl           Create a python gtfs2sl map.
```

By default the `sl2gtfs` utility outputs a comma separated list of site id and stop id.

Usage in a script

```
>>> import sl2gtfs
>>> mapping = sl2gtfs.create(sl_site_data_url='http://...', sl_gtfs_agency_stop_url='http://...')
>>> for site_id, stop_id in mapping[:2]:
...   print(site_id, stop_id)
...
(u'6790', '7468273')
(u'6791', '7411302')
```

## Development & Release

To install it while still working on your changes.

    pip install -e .

Package

    python setup.py sdist

Release

    twine upload dist/*

