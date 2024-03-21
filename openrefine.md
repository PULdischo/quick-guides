# OpenRefine
OpenRefine is a free, open source tool for working with messy data. It is used to explore, clean (standardize), manipulate, and structure your data. It can also utilize web services and external data to expand and link your data.

OpenRefine is a great way to transform your data without altering the original file because all your work is completed within the software application.

![openrefine logo image](/img/openrefine.png)

See OpenRefine's [homepage](https://openrefine.org/), [download page](https://openrefine.org/download), and [documentation](https://openrefine.org/docs).

## Get Started
OpenRefine is a software application that you must [download](https://openrefine.org/download). After you download the application it will operate in your web browser.

OpenRefine maintains your work as a "project." You have to upload a file, then manipulate that file, and finally export a new file that is different from what you first imported into OpenRefine. That means your initial spreadsheet/dataset does not change unless you use the export of your new file to overwrite your original file.

## Recommended Approach
OpenRefine is most commonly used with tabular data aka a spreadsheet. While you can upload other file types, this guide assumes you are working with a spreadsheet like a .CSV file.

## Create a Project
Launch OpenRefine. Once it opens in your browser, click "create project" in the left navigation bar.

Next, set your project parameters. While you can OpenRefine allows a range of specifications, the following settings are preferred:

- "Name Project:" Your project name will output as your file name when you export your data at the end
- "Character encoding:" UTF-8
- "Columns are separated by:" select commas (CSV)
- Select "parse next" and enter "1" for "line(s) as column header"
- Select "store blank rows" and "store blank cells as null"

Click "create project"

## Navigating the Interface
OpenRefine has a few important interactive interface features. On the left you will find "Facet/Filter" and "Undo/Redo" toggles. This is where you will open different facet and filter windows that will help you explore and edit your data. In the middle and towards the top, you can toggle how many rows of your dataset you will see at a time. Towards the top right, there are options to open a new project or export your current project.

You'll notice each column has a down carrot icon button. If you click the down carrot icon, you will be provided with a drop down menu that lists a number of actions and features to select that will help you explore, clean, manipulate, and structure your data.

## Facets/Filters and Exploring
Facets will help you explore patterns in your data and find errors or inconsistencies. You can use facets to isolate rows containing similar data to facilitate further exploration or editing. Below are a few facet and filters followed by the menu path and a short description.

- Text facet: drop down > facet > text facet; Groups the data in the column by all the text in a cell
- Word facet: drop down > facet > customized facet > word facet; Isolates individual words even within one cell and then groups each individual word
- Text filter: drop down > text filter; Operates as a word search and then isolates those values

The facet/filter window on the left of your screen will compile any recurring value/data/information within the column where you selected a facet. The value will be listed and then a number to the right will show how many times that value appears in that column. This is an easy way to find typos or differences (like an extra space or a lower case 'l' masquerading as an upper case 'I') that are difficult to spot with the human eye, but will create problems for a computer.

Use OpenRefine's documentation to learn about other facets not covered here.

## Structuring
OpenRefine makes it easy to move, combine, add, and rename columns. Use the drop down menu and the "Edit column" section to access column transformation options.

For example, "Join columns" will allow you to combine multiple columns. If you have a date divided into a day, month, and year column, you can use the "Join columns" option to make all three columns into one "date" column.

## Editing
Hover over any cell to make an edit button appear for that cell. Here you can edit the value within the cell and change the data type. Once you've made your changes, you select apply to confirm the edit. You will also notice the option to "Apply to all identical cells" and this is where the real power in OpenRefine lies. Editing multiple cells at the same time minimizes the possibility for human error and is more efficient. 

You can also edit mutliple cells with the the facet/filter window. Hover over a value to make an edit option appear. Select edit, make your change and then select apply. This will change every value grouped in that particular facet.

You can trigger view other cell edits by using the drop down menu and hovering over the "Edit cells" section.

## Undo/Redo
OpenRefine tracks your changes and allows you to move backward and forward through your edit history useing the Undo/Redo feature in the top left. This history will remain even if you shutdown OpenRefine and come back to work at another time.

## Exporting
At a certain point you will want to export your data for use in your research project and/or publication. When you are ready to do this, find the "export" button in the top right corner of your browser. Then select your prefered file type output (while it depends on your initial upload, this guide assumes you will output a "Comma-separated value" (CSV) file). OpenRefine will use your project name as the file name. Once you select your preferred output, OpenRefine will immediately download the file to your default download folder.

## Further Reading
Thomas Padilla, ["Getting Started with OpenRefine"](https://thomaspadilla.org/dataprep/)

## Contributors
This guide was created by Bryan Winston with information derived from lessons provided by [Thomas Padilla](https://thomaspadilla.org/dataprep/) and [Library Carpentry](https://librarycarpentry.org/lc-open-refine/).