---
title: Better Exposed Filters (BEF)
date: 2016-09-29 09:27:21
tags: Drupal
---

## Better Exposed Filters (BEF)
### Because your filters are lame or your client wants something crazy

In Drupal Views, there are things called filters. Filters do just that, they filter content. In other words, you can determine what content (or type of content) should be shown on your webpage. One example of this could be a site with a page for their blogs and a page for their events. Obviously, you wouldn’t want your events to show up as blogs or vice versa, which is why you would use a filter to determine that blogs go on the blogs page and the same goes for events.

What if you wanted to give the visitors to your site an option to filter results even further? Say, they go to the blog page but they only want to see blogs about dogs rather than cats, which is just crazy I know but people ask for these things! In this case, you would want an “exposed filter”. An exposed filter allows the end-user to choose how they want to filter the content on the page, so instead of seeing blogs about dogs and cats, they could see one or the other with your exposed filter. An example of this could be an online store; you can filter out products that are too high or low, etc.

Drupal Views comes with a basic exposed filter but it’s not very easy to use. So, in comes the module: Better Exposed Filters. Yes, it is better! It Provides a better user experience than the default option. 

### **How on earth do you use BEF?**

Allow me to show you



### **Prerequisites**

Have a content type

Have a view set up (View Page or View Block)



### **Step 1: Install and Enable the module**

Using Drush or

Install the module to `/modules` directory



### **Step 2: Taxonomy Terms**

Navigate to `Structure > Taxonomy`

Add vocabulary (This will be your taxonomy grouping title)

Click on "List Terms" in your new Vocabulary

Add your terms (this will be the categories or terms you sort by in your view)



### **Step 3: Term reference field in your content type**

Navigate to your Content Type

(If you don't have one already) Add a field with type of "Term"

It will prompt you to configure your field.

Under field settings, change number of values to 1 if you don't want them to choose multiple taxonomy terms

Point the Vocabulary to your Vocabulary your just created.

Save settings



### **Step 4: Create filter in the view**

Under Filter Criteria, Click add - "Has taxonomy term"

Select your taxonomy Vocabulary

Selection type should be Dropdown

Expose the filter to anon users

Select "Single filter" and change the filter Label to what you want or remove it

Select "Is one of" and select the terms you want selected. (If all, leave terms unselected)



### **Step 5: Enable BEF in the view**

Under Exposed form, change Basic to Better Exposed Filters

Check the option for "Autosubmit" and Make sure "Hide submit button" is checked as well

At the bottom, you should see the your taxonomy term field. You can change it from "Default select list" to "Checkboxes", "Links" or "Hidden"




### **Miscellaneous**

"Exposed form in block: No" will add your filter(s) above your view page.

"Exposed form in block: Yes" allows your to place your filters as a block wherever you want.

BEF must be used with a View Page UNLESS you turn on AJAX in the advanced settings of your view. Then you can use it with your View Block

However, if there is a custom `view.tpl.php`, BEF block may not work on a Block View. You will need to have a Default or normal `view.tpl.php` for your specific view for it to work.
