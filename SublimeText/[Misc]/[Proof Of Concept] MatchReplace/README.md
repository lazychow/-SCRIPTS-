Written in response to this [__StackOverflow question__](http://stackoverflow.com/questions/36242643/replace-the-matched-selections-from-another-file) asking how to replace matched selections between a source & target file.

#Demo:

![Demo](https://raw.githubusercontent.com/Enteleform/-SCRIPTS-/master/SublimeText/%5BMisc%5D/%5BProof%20Of%20Concept%5D%20MatchReplace/Demo.gif)

&nbsp;

-----

#Implementation:

&nbsp;

* get active views of each group in a 2 group window
* find `RegEx` matches of a user-defined array of keys which will be matched at both documents
* store value regions of both documents, and string values of the source document
* sort stored values by region
* iterate over regions at the target document, replacing all matched values from the source

&nbsp;

The demo is written to work with single tier `JSON` files, but can be adjusted as necessary.

`RegEx` patterns to precede & follow `replacementKeys` are:

* `queryPrefix`
* `querySuffix`

&nbsp;

-----

#Usage:

&nbsp;

To use MatchReplace:

* copy the plugin folder to your `Packages` directory
* edit the `replacementKeys` array in the `run` function to suit your match+replace needs
* save the plugin & restart SublimeText
* open a 2-group window layout using <kbd>Shift + Alt + 2</kbd>
* move the document you want as the SOURCE to the left group
* move the document you want to MATCH with the source to the right group
* open the Command Palette with <kbd>Ctrl + Shift + P</kbd> and run the `Match Replace: Demo` command

&nbsp;

###Note:

`replacementKeys` must be an __exact__ match at both documents *( leading whitespace is ignored )*.

If you want to allow for variation within the `replacementKeys`, you will need to implement an additional layer of `RegEx` processing.
