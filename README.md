Deviant Art Ripper
==================

Bulk downloads images from Deviant Art using Mechanicalsoup's simulated browser.


How it Works
------------

Every artist's page on Deviant Art has two primary image sections: gallery and favorites, and both work in a similar manner. Each has a "Featured" and an "All" view, and each has a list down the left side of subcategories (called folders for galleries, and collections for favorites).

We use this pattern to make the command line interface easier:

 * Specify the artist to download from
 * Specify gallery or favorites
 * Optionally specify the subcategory (defaults to ALL)
 * Optionally specify a query (searched using the "Search Gallery" or "Search Favorites" search box)

### Subcategories

These are seen as folders in the gallery, and collections in favorites. The program takes whatever you specify for a subcategory and chooses the first subcategory that **ends** with the text you provided (note: it is case sensitive).

There are three special subcategories: SCRAPS, FEATURED, and ALL, which match up to special categories in Deviant Art. SCRAPS only works in the galleries section.


Usage
-----

	darip [-h] [-g | -f] [-s SUBCATEGORY] [-q QUERY] [-p PATH] [-P] [-D] artist

	positional arguments:
	  artist                Select artist

	optional arguments:
	  -h, --help            show this help message and exit
	  -g, --gallery         Look in the artist's gallery
	  -f, --favorites       Look in the artist's favorites
	  -s SUBCATEGORY, --subcategory SUBCATEGORY
	                        Specify a subcategory of the artist's favorites or
	                        gallery. It will select the first subcategory that
	                        ENDS with the specified text. Special categories:
	                        SCRAPS, FEATURED, ALL (default ALL)
	  -q QUERY, --query QUERY
	                        Execute a search query inside the selected
	                        gallery/favorites/category
	  -p PATH, --path PATH  Path to save images to. (default current directory)
	  -P, --printonly       Only print the file names, don't download
	  -D, --debug           Print debug information during operation

Note: You must specify either gallery `-g` or favorites `-f`.


Installation
------------

Via pip:

    pip install darip

Via setup.py:

    python setup.py install


Dependencies
------------

 * fake_useragent: https://pypi.org/project/fake-useragent/
 * mechanicalsoup: https://pypi.org/project/MechanicalSoup/


License
-------

https://opensource.org/licenses/MIT

Copyright 2018 Karl Stenerud

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
