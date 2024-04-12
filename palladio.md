# Palladio
Palladio, developed by Stanford’s Humanities + Design Lab, is a web-based visualization tool for
maps, network graphs, and data tables. While the amount of data that can be used with this tool
might be somewhat limited, the selling point of this tool is the ease with which visualizations can
be generated and the breath of type of visualizations. The same data can be quickly viewed in a
variety of ways.

![image of mapping visualization feature on palladio, showing a map of connections between locations spanning the atlantic ocean](/img/palladio.png)

See tool's [homepage](https://hdlab.stanford.edu/palladio/) and [tutorials](https://hdlab.stanford.edu/palladio/help/). 

## Get started
Palladio is an online web-based platform, so there is no need to install
anything. Go to http://hdlab.stanford.edu/palladio/ to get started. The
most common way to add data to Palladio is to drag a CSV file into the
site.

## Review the data
After you have added data to Palladio, review the results of the data
import. Fields that contain data that Palladio find questionable, will be
highlighted with a red dot. Click on the dot to learn more about the fields.
Also notice that Palladio has attempted to discover the datatypes of your
fields. Correct this if necessary. If any of the data in your fields is not
immediately necessary, hide it by clicking the ‘eye’ icon. The data will
still be there, but the tool will be much easier to use.

## Map
Maps in Palladio, and indeed most geo-location software, are a series of
layers. Palladio provides you with a base layer that contains grey outlines of landmasses. Three types of
layers may be added to your map: Data, Tiles, and Shapes. Data corresponds to specific points in the form of
coordinates in your data. Tiles refers to online sources of base maps. (Maps are stored in sets of tiles for faster
loading)

You may choose a different base layer by clicking the Tiles tab and then selecting a layer. You can then
remove the grey landmass layer.

You may add a Data layer by clicking New Layer and then the Data tab. Click the box labeled Places to select
the column of data that contains coordinate information. You can also check off ‘Size points’ to select a
numeric column data with which to determine the size of points on the map.

## Graph
Graphs are visualizations of relationships between entities. Graphs in
Palladio are generated based on the two actors involved in these
relationships. You indicate a relationship between two points of data by
indicating one as the source of the relationship and another as the
target. There is no concept of directionality in Palladio. In other
words,source and target do not give any indication that one is doing
something to the other, but rather simply that there is a relationship of
some sort between the two.
Select one column of data to be your source by clicking the box next to
Source and another to be your target by doing the same next to Target.
Table and Gallery
Table and Gallery provide ways to get a full view of the data you are
dealing with. The Gallery has the added benefit of being able to
transform web addresses (URLs) of images on the web into embedded
images.

## Facet/Filter
At the bottom of the screen is a
very important feature of Palladio: the Facet tool. This tool allows you
to restrict or select the category of data you would like to view. This
filter works with all the above-mentioned tools.

Click Facet and then in the bottom right, select the field by which you
would like to restrict the data. You should then be presented with a list
of the unique values from that column. You may click any of those
values to restrict the main visualization window to just records in your
data that contain that unique value.

## Further reading
Miriam Posner, "[Getting Started with Palladio](http://miriamposner.com/blog/getting-started-with-palladio/)"

## Contributors
This guide was created at the McGraw Center by Ben Johnson, in the "[Quickguide to Palladio](https://mcgrawect.princeton.edu/guides/Quickstart-Guide-Palladio.pdf)." It has been adapted by Filipa Calado.


