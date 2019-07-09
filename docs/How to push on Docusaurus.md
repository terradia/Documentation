# How to add a document

## Document

Document have to be placed in the /docs directory a the root of the repository

````
Documentation
├───docs
└───website
    ├───blog
    ├───core
    ├───pages
    │   └───en
    └───static
        ├───css
        └───img
````

The default title of the document is the document's filename. If you want to change the title you must add a basic table at the top of the document like this:

````
---
id: the filename without the .md file extention
title: the new title
---
````

## Sidebar

When the document is in the /docs directory go to /website and edit the sidebars.json file
````
{
	"docs": {
		"category 1": [
			"doc 1",
			"doc 2"
		],
		"category 2": [
			"doc 3",
			"doc 4"
		]
	}
}
````
Inside the docs object there are some category that contain an array of string, these strings are basically the document's filename without the .md extension and the category are here for organizational purpose.

You can add a category by adding a ````,```` after the the last ````]```` or between two other category. then like the other ones add the category name as a string and put ````[]```` after the ````:````

Add then the document's filename inside the desired category as a string.

After adding the document, commit and push it to the github. After 1 or 2 minutes your document will be online
