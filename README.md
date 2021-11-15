[![](https://img.shields.io/pypi/pyversions/python-fontbro.svg?color=blue&logo=python&logoColor=white)](https://www.python.org/)
[![](https://img.shields.io/pypi/v/python-fontbro.svg?color=blue&logo=pypi&logoColor=white)](https://pypi.org/project/python-fontbro/)
[![](https://pepy.tech/badge/python-fontbro)](https://pepy.tech/project/python-fontbro)
[![](https://img.shields.io/github/stars/fabiocaccamo/python-fontbro?logo=github)](https://github.com/fabiocaccamo/python-fontbro/)
[![](https://badges.pufler.dev/visits/fabiocaccamo/python-fontbro?label=visitors&color=blue)](https://badges.pufler.dev)
[![](https://img.shields.io/pypi/l/python-fontbro.svg?color=blue)](https://github.com/fabiocaccamo/python-fontbro/blob/master/LICENSE.txt)

[![](https://img.shields.io/travis/fabiocaccamo/python-fontbro?logo=travis&label=build)](https://travis-ci.org/fabiocaccamo/python-fontbro)
[![](https://img.shields.io/circleci/build/gh/fabiocaccamo/python-fontbro?logo=circleci&label=build)](https://circleci.com/gh/fabiocaccamo/python-fontbro)
[![](https://img.shields.io/codecov/c/gh/fabiocaccamo/python-fontbro?logo=codecov)](https://codecov.io/gh/fabiocaccamo/python-fontbro)
[![](https://img.shields.io/codacy/grade/fc40788ae7d74d1fb34a38934113c4e5?logo=codacy)](https://www.codacy.com/app/fabiocaccamo/python-fontbro)
[![](https://img.shields.io/codeclimate/maintainability/fabiocaccamo/python-fontbro?logo=code-climate)](https://codeclimate.com/github/fabiocaccamo/python-fontbro/)
[![](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

# python-fontbro
human-friendly font operations. :tumbler_glass:

## Index
-   [Installation](#installation)
-   [Usage](#usage)
-   [Testing](#testing)
-   [License](#license)

## Installation

```bash
pip install python-fontbro
```

## Usage

Just import the font class:

```python
from fontbro import Fontbro

font = Fontbro(filepath='MyFont.ttf')
```

### Methods

-   [`get_characters`](#get_characters)
-   [`get_characters_count`](#get_characters_count)
-   [`get_features`](#get_features)
-   [`get_format`](#get_format)
-   [`get_name`](#get_name)
-   [`get_names`](#get_names)
-   [`get_script_by_character`](#get_script_by_character)
-   [`get_script_by_code`](#get_script_by_code)
-   [`get_scripts`](#get_scripts)
-   [`get_style_flags`](#get_style_flags)
-   [`get_ttfont`](#get_ttfont)
-   [`get_variable_axes`](#get_variable_axes)
-   [`get_variable_axis_by_tag`](#get_variable_axis_by_tag)
-   [`get_variable_axes_tags`](#get_variable_axes_tags)
-   [`get_variable_instances`](#get_variable_instances)
-   [`get_variable_instance_closest_to_coordinates`](#get_variable_instance_closest_to_coordinates)
-   [`get_weight`](#get_weight)
-   [`get_width`](#get_width)
-   [`is_static`](#is_static)
-   [`is_variable`](#is_variable)
-   [`save`](#save)
-   [`save_as_woff`](#save_as_woff)
-   [`save_as_woff2`](#save_as_woff2)
-   [`set_name`](#set_name)
-   [`set_names`](#set_names)
-   [`set_style_flags`](#set_style_flags)
-   [`subset`](#subset)

-   #### get_characters
```python
"""
Gets the font characters.

:returns: The characters.
:rtype: generator of dicts
"""
chars = font.get_characters()
```

-   #### get_characters_count
```python
"""
Gets the font characters count.

:returns: The characters count.
:rtype: int
"""
chars_count = font.get_characters_count()
```

-   #### get_features
```python
"""
Gets the font opentype features.

:returns: The features.
:rtype: list of dict
"""
features = font.get_features()
```

-   #### get_format
```python
"""
Gets the font format: otf, ttf, woff, woff2.

:param ignore_flavor: If True, the original format without compression will be returned.
:type ignore_flavor: bool

:returns: The format.
:rtype: str or None
"""
font.get_format(ignore_flavor=False)
```

-   #### get_name
```python
"""
Gets the name by its identifier from the font name table.

:param key: The name id or key (eg. 'family_name')
:type key: int or str

:returns: The name.
:rtype: str or None
"""
family_name = font.get_name(key=Fontbro.NAME_FAMILY_NAME)
```

-   #### get_names
```python
"""
Gets the names records mapped by their property name.

:returns: The names.
:rtype: dict
"""
names = font.get_names()
```

-   #### get_script_by_character
```python
"""
Gets the script by character.

:param char: The character
:type char: str

:returns: The script by character.
:rtype: dict
"""
script = font.get_script_by_character(char='a')
```

-   #### get_script_by_code
```python
"""
Gets the script by unicode code point.

:param code: The code
:type code: int

:returns: The script by code.
:rtype: dict
"""
script = font.get_script_by_code(code=34)
```

-   #### get_scripts
```python
"""
Gets the scripts supported by the font.

:returns: The scripts.
:rtype: list of dict
"""
scripts = font.get_scripts()
```

-   #### get_style_flags
```python
"""
Gets the style flags reading OS/2 and macStyle tables.

:returns: The dict representing the style flags.
:rtype: dict
"""
flags = font.get_style_flags()
```

-   #### get_ttfont
```python
"""
Gets the wrapped TTFont instance.

:returns: The TTFont instance.
:rtype: TTFont
"""
ttfont = font.get_ttfont()
```

-   #### get_variable_axes
```python
"""
Gets the font variable axes.

:returns: The list of axes if the font is a variable font otherwise None.
:rtype: list of dict or None
"""
axes = font.get_variable_axes()
```

-   #### get_variable_axis_by_tag
```python
"""
Gets a variable axis by tag.

:param tag: The tag
:type tag: string

:returns: The variable axis by tag.
:rtype: dict or None
"""
axis = font.get_variable_axis_by_tag(tag='wght')
```

-   #### get_variable_axes_tags
```python
"""
Gets the variable axes tags.

:returns: The variable axis tags.
:rtype: list or None
"""
axes_tags = font.get_variable_axes_tags()
```

-   #### get_variable_instances
```python
"""
Gets the variable instances.

:returns: The list of instances if the font is a variable font otherwise None.
:rtype: list of dict or None
"""
instances = font.get_variable_instances()
```

-   #### get_variable_instance_closest_to_coordinates
```python
"""
Gets the variable instance closest to coordinates.
eg. coordinates = {'wght': 1000, 'slnt': 815, 'wdth': 775}

:param coordinates: The coordinates
:type coordinates: dict

:returns: The variable instance closest to coordinates.
:rtype: dict or None
"""
instance = font.get_variable_instance_closest_to_coordinates(coordinates={'wght': 1000, 'slnt': 815, 'wdth': 775})
```

-   #### get_weight
```python
"""
Gets the font weight value and name.

:returns: The weight name and value.
:rtype: dict or None
"""
weight = font.get_weight()
```

-   #### get_width
```python
"""
Gets the font width value and name.

:returns: The width name and value.
:rtype: dict or None
"""
width = font.get_width()
```

-   #### is_static
```python
"""
Determines if the font is a static font.

:returns: True if static font, False otherwise.
:rtype: bool
"""
static = font.is_static()
```

-   #### is_variable
```python
"""
Determines if the font is a variable font.

:returns: True if variable font, False otherwise.
:rtype: bool
"""
variable = font.is_variable()
```

-   #### save
```python
"""
Saves the font at filepath.

:param filepath: The filepath, if None the source filepath will be used
:type filepath: str or None
:param overwrite: The overwrite, if True the source font file can be overwritten
:type overwrite: bool

:returns: The filepath where the font has been saved to.
:rtype: str

:raises ValueError: If the filepath is the same of the source font and overwrite is not allowed.
"""
saved_font_path = font.save(filepath=None, overwrite=False)
```

-   #### save_as_woff
```python
"""
Saves font as woff.

:param filepath: The filepath
:type filepath: str
:param overwrite: The overwrite, if True the source font file can be overwritten
:type overwrite: bool

:returns: The filepath where the font has been saved to.
:rtype: str
"""
saved_font_path = font.save_as_woff()
```

-   #### save_as_woff2
```python
"""
Saves font as woff2.

:param filepath: The filepath
:type filepath: str
:param overwrite: The overwrite, if True the source font file can be overwritten
:type overwrite: bool

:returns: The filepath where the font has been saved to.
:rtype: str
"""
saved_font_path = font.save_as_woff2()
```

-   #### set_name
```python
"""
Sets the name by its identifier in the font name table.

:param key: The name id or key (eg. 'family_name')
:type key: int or str
:param value: The value
:type value: str
"""
font.set_name(Fontbro.NAME_FAMILY_NAME, 'Family Name Renamed')
```

-   #### set_names
```python
"""
Sets the names by their identifier in the name table.

:param names: The names
:type names: dict
"""
font.set_names(names={
    Fontbro.NAME_FAMILY_NAME: 'Family Name Renamed',
    Fontbro.NAME_SUBFAMILY_NAME: 'Regular Renamed',
})
```

-   #### set_style_flags
```python
"""
Sets the style flags, flags set to None will be ignored.

:param bold: The bold flag value.
:type bold: bool or None
:param italic: The italic flag value.
:type italic: bool or None
:param underline: The underline flag value.
:type underline: bool or None
:param outline: The outline flag value.
:type outline: bool or None
"""
font.set_style_flags(regular=None, bold=None, italic=None, outline=None, underline=None)
```

-   #### subset
```python
"""
Subsets the font using the given options (unicodes or glyphs or text),
it is possible to pass also subsetter options, more info here:
https://github.com/fonttools/fonttools/blob/main/Lib/fontTools/subset/__init__.py

:param unicodes: The unicodes
:type unicodes: str or list
:param glyphs: The glyphs
:type glyphs: list
:param text: The text
:type text: str
:param options: The subsetter options
:type options: dict
"""
font.subset(unicodes='', glyphs=[], text='', **options)
```

## Testing
```bash
# create python virtual environment
virtualenv testing_fontbro

# activate virtualenv
cd testing_fontbro && . bin/activate

# clone repo
git clone https://github.com/fabiocaccamo/python-fontbro.git src && cd src

# install requirements
pip install --upgrade pip
pip install -r requirements.txt
pip install -r requirements-dev.txt

# run tests using tox
tox

# or run tests using unittest
python -m unittest

# or run tests using setuptools
python setup.py test
```

## License
Released under [MIT License](LICENSE.txt).

---

## See also

- [`python-benedict`](https://github.com/fabiocaccamo/python-benedict) - dict subclass with keylist/keypath support, I/O shortcuts (base64, csv, json, pickle, plist, query-string, toml, xml, yaml) and many utilities. 📘
- [`python-fsutil`](https://github.com/fabiocaccamo/python-fsutil) - file-system utilities for lazy devs. 🧟‍♂️
