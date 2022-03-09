# Password requirements dataset

[![Node.js CI](https://github.com/strugee/password-requirements-dataset/actions/workflows/node.js.yml/badge.svg)](https://github.com/strugee/password-requirements-dataset/actions/workflows/node.js.yml)

This repository contains a database of password limits that different websites impose. The major focus is on limits that are arbitrary, indicate some underlying insecure design, or prevent the usage of strong passwords (e.g. because strong passwords crash the website).

## Goals

This the overarching, ambitious goal of this project is to improve the state of internet password security by doing two things:

1. Helping users pick the strongest passwords they are allowed to for websites
2. Enabling public shaming of websites that don't get this right

Eventually it would be awesome if this data was used by password managers to generate even stronger passwords, without having to make conservative choices for broad compatibility. But the data included is designed to be flexible and detailed enough to enable all sorts of applications that haven't even been thought of yet.

## Usage

Each entry in the dataset is represented in a JSON file in the `data/` directory. Copyright is waived on this data (see "License" below), so you are welcome to do whatever you want with it. That being said, if you build tooling around this dataset - for example, to load it into a SQLite database so it can be efficiently queried, or a hall of shame page for websites with bad password practices - you are _highly_ encouraged to submit either your tool itself or a link to your tool in a Pull Request.

More information on the format of each entry is forthcoming. In the meantime, you can use the (mostly-complete) JSON Schema in `schema.json` as a reference point.

### `meta.json`

`meta.json` contains meta-information about the dataset. Currently it has only one key, `schema-version`, which will be increased every time the schema is updated in a backwards-incompatible way. It will not be changed if backwards-compatible additions are made.

Note that the addition of new enum values is _**not**_ considered backwards-incompatible. Therefore, you should expect to handle the following:

* Unknown properties
* Unknown `issue_name` values
* Unknown issue `type` values
* Unknown issue `source` values (and therefore, unknown `additional_sources` values)

For most applications, it would probably be sensible to ignore anything you don't understand.

## Author

AJ Jordan <alex@strugee.net>

## License

<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <span resource="[_:publisher]" rel="dct:publisher">
    <span property="dct:title">AJ Jordan</span></span>
  has waived all copyright and related or neighboring rights to
  <span property="dct:title">Password requirements dataset</span>.
This work is published from:
<span property="vcard:Country" datatype="dct:ISO3166"
      content="US" about="[_:publisher]">
  United States</span>.
</p>
