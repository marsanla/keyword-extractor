#Keyword Extractor

A simple [NPM package](https://npmjs.org/package/keyword-extractor) for extracting _keywords_ from a string by
removing stopwords.

## Installation

```sh
$ npm install keyword-extractor
```

## Running tests

To run the test suite, first install the development dependencies by running the following command within the package's
directory.

```sh
$ npm install
```

To execute the package's tests, run:

``` sh
$ make test
```

##Usage of the Module

```javascript
//  include the Keyword Extractor
var keyword_extractor = require("keyword-extractor");

//  Opening sentence to NY Times Article at
//  http://www.nytimes.com/2013/09/10/world/middleeast/surprise-russian-proposal-catches-obama-between-putin-and-house-republicans.html
var sentence = "President Obama woke up Monday facing a Congressional defeat that many in both parties believed could hobble his presidency."

//  Extract the keywords
var extraction_result = keyword_extractor.extract(sentence,{
                                                                language:"english",
                                                                remove_digits: true,
                                                                return_changed_case:true
                                                           });

/*
  extraction result is:

  [
        "president",
        "obama",
        "woke",
        "monday",
        "facing",
        "congressional",
        "defeat",
        "parties",
        "believed",
        "hobble",
        "presidency"
    ]
*/
```

###Options Parameters

The second argument of the _extract_ method is an Object of configuration/processing settings for the extraction.

Parameter Name | Description | Permitted Values
---------------|-------------|-----------------
language       | The stopwords list to use. | _english_ or _spanish_
return_changed_case | The case of the extracted keywords. Setting the value to _true_ will return the results all lower-cased, if _false_ the results will be in the original case. | _true_ or _false_

## Credits

The initial stopwords lists are taken from the following sources:

- English [http://jmlr.org/papers/volume5/lewis04a/a11-smart-stop-list/english.stop]
- Spanish [https://stop-words.googlecode.com/svn/trunk/stop-words/stop-words/stop-words-spanish.txt]
