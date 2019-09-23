# OmegaT FakeMT plugin

This plugin let you add a custom remote Machine Translator. You can configure four parameters in the MT configuration window.

* __URL__: the URL to connect to
* __source__: The name of the source parameter that will take the source language.
* __target__: The name of the target parameter that will take the target language.
* __source__: The name of the text parameter that will take the content of the segment to be translated.

`GET ${url}?${source}=en-US&${target}=fr-FR&${text}=Hello World!` 

New release, by Thomas Cordonnier, enables more generic support for any MT engine: the result can be either in XML or in JSON, 
and you can specify which part of the result is returned to OmegaT:

* if format is XML, you specify the part to be returned to the client using XPath
* if format is JSON, you specify the part to be returned to the client using JsonPath (https://goessner.net/articles/JsonPath/)

## Caveat

There are currently several limitations, for this plugin:

* only one custom MT can be used,
* the HTTP method used is always GET
* When changing the name of the MT, the changes are effective after restarting the application

## Installation

You can get a plugin jar file from zip/tgz distribution file.
OmegaT plugin should be placed in `$HOME/.omegat/plugins` or `C:\Program Files\OmegaT\plugins`
depending on your operating system.

To run the test MT server, you have to install Node.js, then run the following commands :

```
$ npm install
$ npm start

  [...]
  Fake TM Server listening on port 8877!
```

## License

This project is distributed under the GNU general public license version 3 or later.

