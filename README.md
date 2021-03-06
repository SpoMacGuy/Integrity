# Integrity

The purpose of Integrity is to make it easy to integrate Open Source projects into your Omnis Studio library.

Once you have included particular clases into your library, if there are changes made to the included library, how to you integrate them back into your library? As you have more and more Open Source projects included in your work, this become more difficult.

Enter Integrity.

To use Integrity, it is expected you are using Git, or some other source management software, and that you have each of the projects as folders in the same directory. For example, say you have your main project "MyGreatCRM" that includes 2 Open Source projects called CSS and OmnisTAP.

We are assuming under your local Git directory you have at least the following 3 folders with your JSON version of your libraries: MyGreatCRM, CSS, OmnisTAP.

When you start up Integrity, you select MyGreatCRM as your main library. It will look in any task within the JSON library folders for the $construct method. In that method it looks for a line (normally a comment) that contains "Requires:". It parses out the rest of the line to find the library and class needed for this library.

The line looks something like this: Requires: CSS.lbs:oCSS

When it runs, it looks for a folder called "CSS" in at the same level in the directory tree as your main library, then looks for a folder named "oCSS" under that folder. It then finds a folder within your main library directory tree with the same name and replaces it. This lets you keep any new changes that are made to the Open Source project current in your library.
