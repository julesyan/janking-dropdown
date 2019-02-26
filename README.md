# Dropdown
Originally developed by [Janking](https://github.com/Janking). Original repo can be found [here](https://github.com/Janking/dropdown)

This repo is not a forked version as it only contains the JS and CSS files that are needed for usage. This may be forked later on and will be linked if it is.

#### Notes
- This only contains English prompts (original is Chinese from my knowledge)
- This has not been fully tested, there may be some functionality that may bug out

### To Do
- [ ] Document all changes from original version
- [ ] 


## Changes
1. Changed prompts to more basic default prompts in English
2. Added a listener that runs when an item is selected. Set this when creating the dropdown. Function takes in the selected item (original item from data):
   ```
   let dropdown = $(selector).dropdown({
     selectListener : function(selectedItem){}
   });
   ```
   
   This can also be manually run if needed (selectedItem should be formatted as in data):
   ```
   dropdown.notifySelectListener(selectedItem);
   ```
   
   This also can be set dynamically. This will replace any function that was present beforehand:
   ```
   dropdown.setSelectListener(callback);
   ```
3. Added a listener that runs when an item is unselected. Set this when creating the dropdown. Function takes in the unselected item (original item from data):
   ```
   let dropdown = $(selector).dropdown({
     delListener : function(selectedItem){}
   });
   ```
   
   This can also be manually run if needed (selectedItem should be formatted as in data):
   ```
   dropdown.notifyDeleteListener(selectedItem);
   ```
   
   This also can be set dynamically. This will replace any function that was present beforehand:
   ```
   dropdown.setDeleteListener(callback);
   ```
4. Allowed data items to have types (this is independent from grouping) if needed beyond basic grouping. This will also be in the class of the item (this was added for the specific usage that I needed, it may not be useful to most users)
5. Added a data field to data items. This will allow users to store any extra data associated with the data item that is not already in the default fields. 
6. Created an addItem function that allows additional items to be added dynamically to the dropdown. This will automatically select the new item also. (this was added for specific usage that I needed. It may be similar to update, but I was unsure of what update was initally designed for)