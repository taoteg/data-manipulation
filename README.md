# Data Manipulation

## Abstract

A presentation on general principles and practices common to data science including:

* Data lifecycles
* Data management
* Data mining
* Data pipelines
* ETL workflows
* Data analytics & analysis  [pending]
* Data processing (CLI, scripts)  [pending]
* Data manipulation (with SQL DDL & DML)  [pending]
* OLDB, OLTP, OLAP, Data Warehouses  [pending]
* Big data  [pending]
* Machine learning  [pending]
* Related resources  [pending]

### Get the Slides

Get slides here: https://github.com/jgentle/data-manipulation

Clone or download as preferred.

### Setup Instructions

Follow these steps to run the slideshow:

1) Install NodeJS (v7.9.0 was used in preparation of this presentation).

    Get the latest version of Node here: https://nodejs.org/en/

1) Install Bower.io and Grunt (requires NodeJS):
    ```
    $ npm install -g bower
    $ npm install -g grunt-cli
    ```

1) Install all the node dependencies:
    ```
    $ npm install
    ```

1) Install all the bower dependencies:
    ```
    $ bower install
    ```

1) Start the presentation:
    ```
    $ grunt serve
    ```
1) A browser window should automatically open to:
    ```
    http://localhost:9000/
    ```

    If the browser does not open automatically, you can manually open one and enter the URL.

1) Enjoy!

### Presentation Controls

Navigate the slide show with these controls:

  * left & right arrows to move through slides horizontally.
  * up & down arrows to drill into slide columns.
  * escape key to see all slides (then arrows to nav to a specific slide)
    * These configs can be overridden if desired.
  * use s to enter speaker view mode in another window.
  * use b to pause and blackout the presentation.
  * select "View > Enter Full Screen" in your browser menu for the best fullscreen performance.
  * you can also use f to enter fullscreen, esc to exit fullscreen - but there is a bug in the background color styles that may bork the presentation design.

### Printing the Presentation to PDF

The presentation can be converted to print ready format by running it as usual then opening a customized version of the URL in your browser and following the usual CTRL/CMD+P conventions for printing to PDF or paper.

*Note that the presentation will look garbled on the screen but will be correct in the print preview and in the PDF/files produced by the print process.*

1) grunt serve

1) Append *?print-pdf* to the end of the url like so:
    ```
    http://localhost:9000/?print-pdf
    ```
1) CTRL/CMD+P to open the print dialog window.

1) Print as desired.

### Presentation History

  2017.06.22 Texas Advanced Computing Center - Summer Institute 2017 - Data and Information Analytics - Seminar: Data Manipulation (ETL)

### Additional Notes

This slide deck is a work-in-progress and will continue to be updated as new content is added or old content is updated.

If you want to create a similar presentation for yourself, you can get the revealJS project code here: https://github.com/hakimel/reveal.js

There is also a yeoman generator for rapid presentation development found here: https://github.com/slara/generator-reveal
