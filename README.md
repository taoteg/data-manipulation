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

1) Install Bower.io (requires NodeJS):
    ```
    $ npm install -g bower
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
  * select "View > Enter Full Screen" in your browser menu for the best fullscreen performance.
  * you can also use f to enter fullscreen, esc to exit fullscreen - but there is a bug in the background color styles that may bork the presentation design.

### Presentation History

  2017.06.22 Texas Advanced Computing Center Summer Institute - Data Manipulation (ETL) for Info Visualization.

### Additional Notes

This slide deck is a work-in-progress and will continue to be updated as new content is added or old content is updated.

If you want to create a similar presentation for yourself, you can get the revealJS project code here: https://github.com/hakimel/reveal.js
