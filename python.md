#options_parser
```python
usage = "usage: %prog [options]"
parser = OptionParser(usage=usage)
parser.add_option("-v", "--verbose",
                  action="store_true", dest="verbose", default=False,
                  help="verbose output, include more detail")
(options, args) = parser.parse_args()
zkclient.options = options
```
