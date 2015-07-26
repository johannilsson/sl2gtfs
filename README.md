# sl2gtfs

Python helpers for converting between SL site ids and national stop ids used by GTFS feeds in Sweden.

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

By default the `sl2gtfs` script outputs a comma separated list of site id and stop id.

In a script

```
>>> import sl2gtfs
>>> mapping = sl2gtfs.create(sl_site_data_url='http://...', sl_gtfs_agency_stop_url='http://...')
>>> for site_id, stop_id in mapping[:2]:
...   print(site_id, stop_id)
...
(u'6790', '7468273')
(u'6791', '7411302')
```

## Development

To install it while still working on your changes.

    pip install -e .

Package

    python setup.py sdist

Release

    twine upload dist/*