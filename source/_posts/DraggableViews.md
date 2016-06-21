---
title: DraggableViews: a HowTo
date: 2016-06-20 21:51:04
tags:
---


## DraggableViews: a HowTo

Drupal views are great! However, the order in which your content prints out isn’t as easy to control. You can sort ascending or descending based on the post date, the title, etc. But what if you had a specific order you wanted them to print out? With Draggableviews you can set the order your content will print out with an easy drag-and-drop gui. Setting draggable views up is a little complex, so let’s walk through the process.

Let’s assume you already have a view set up…

### Setting up your Draggable Display

1. Enable the module
2. Navigate to your view <img src="http://i.imgur.com/aYdUlcE.png">
3. Add a new Page to your view            
4. Set a page source - I usually use something like /draggable-blog <img src="http://i.imgur.com/gAsa1Vp.png">
5. Set your format to Table <img src="http://i.imgur.com/8PVBLzC.png">
6. Make sure your fields includes Content: Title
7. Add DraggableViews: Content to your fields <img src="http://i.imgur.com/W24ljWY.png">
8. Add DraggableViews: Weight (ascending) to your sort criteria <img src="http://i.imgur.com/f5m92Lb.png">  

### Setting your original view to use your draggable order

1. Navigate to your original view
2. Add DraggableViews: Weight (ascending) to your sort criteria and remove the default sort criteria - (should be Post Date)
3. You’ll be asked to Display Sort as: and you will select your View in the dropdown. In this case my view name is Test View: <img src="http://i.imgur.com/XgW87B8.png">

Once you have all this setup, navigate to your /draggable page. Once you are on that page, you will see a list of your content with the draggable icon on the left side. Order them in the way you like and click save. Now your view is sorted in such a way that you can easily manage.
