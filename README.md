# Javascript assets for Localgov Drupal

This library provides a wrapper around various javascript libraries required by certian modules of the Localgov profile. It should be required by default when installing Localgov Drupal and will pull down necessary libraries to the docroot libraries directory.

## Current asset libraries
- enyo/dropzone (6.0.0-beta2)
  To support Dropzone and Simple bulk media upload.

## Overriding these assets

If you wish to download these libraries another way, or replace them with different versions, you can replace this library or individual libraries. 
Within your sites root composer.json file use:
```json
"replace": {
    "localgovdrupal/localgov_assets" : "*"
}
```
or for an individual library:
```json
"replace": {
    "enyo/dropzone" : "*"
}
```

Then require the libraries you need in your preffered way.

Eg. To upgrade dropzone to a fork you could use
```json
"repositories": {
    "dropzone": {
        "type": "package",
        "package": {
            "name": "nicolascarpi/dropzone",
            "version": "7.2.0",
            "type": "drupal-library",
            "dist": {
                "url": "https://github.com/NicolasCARPi/dropzone/archive/refs/tags/7.2.0.zip",
                "type": "zip"
            }
        }
    }
},
"require": {
    "nicolascarpi/dropzone": "^7.2.0"
}
```
