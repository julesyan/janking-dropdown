# Dropdown
Originally developed by [Janking](https://github.com/Janking). Original repo can be found [here](https://github.com/Janking/dropdown). Most/All additions and changes were due to using this plugin for an application, they may or may not be useful. Any feedback would be welcome. There are some additions that may be similar to existing functionality (such as the preexisting update and bind functions), but since it was extremely unclear on how to use any of them, I decided to develop those functionalities on my own with clear instructions.

This repo is not a forked version as it only contains the JS and CSS files that are needed for usage. This may be forked later on and will be linked if it is.

#### Notes
- This only contains English prompts (original is Chinese from my knowledge)
- This has not been fully tested, there may be some functionality that may bug out
- There may be repeated functionality form the original, but since I could not figure out how to use some of the functions, I opted for adding custom functionality

### To Do
- [x] Document all changes from original version <sub>(added Feb 26, 2019 | completed Feb 26, 2019)</sub>
- [x] Remove testing logs <sub>(added Feb 26, 2019 | completed Feb 26, 2019)</sub>
- [x] Fix dropdown appending to <sub>(added Feb 26, 2019 | completed Feb 26, 2019)</sub>
- [x] Upload all final changes to GitHub <sub>(added Feb 26, 2019 | completed Feb 26, 2019)</sub>
- [ ] Fork original repo and submit feature request update to Janking <sub>(added Feb 26, 2019)</sub>
- [x] Add delete item feature <sub>(added Feb 27, 2019 | completed Feb 27, 2019)</sub>
- [x] Get data based on type <sub>(added Feb 27, 2019 | completed Feb 27, 2019)</sub>
- [x] Dynamically change entire selected items <sub>(added March 14, 2019 | completed Mach 19, 2019)</sub>
- [ ] Select an already existing item <sub>(added March 19, 2019)</sub>
- [ ] Unselect an already existing item <sub>(added March 19, 2019)</sub>


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
   dropdown.data().dropdown.notifySelectListener(selectedItem);
   ```

   This also can be set dynamically. This will replace any function that was present beforehand:
   ```
   dropdown.data().dropdown.setSelectListener(callback);
   ```
3. Added a listener that runs when an item is unselected. Set this when creating the dropdown. Function takes in the unselected item (original item from data):
   ```
   let dropdown = $(selector).dropdown({
     delListener : function(selectedItem){}
   });
   ```

   This can also be manually run if needed (selectedItem should be formatted as in data):
   ```
   dropdown.data().dropdown.notifyDeleteListener(selectedItem);
   ```

   This also can be set dynamically. This will replace any function that was present beforehand:
   ```
   dropdown.data().dropdown.setDeleteListener(callback);
   ```
4. Allowed data items to have types (this is independent from grouping) if needed beyond basic grouping. This will also be in the class of the item (this was added for the specific usage that I needed, it may not be useful to most users)
5. Added a data field to data items. This will allow users to store any extra data associated with the data item that is not already in the default fields.
6. Created an addItem function that allows additional items to be added dynamically to the dropdown. This will automatically select the new item also.
   ```
   dropdown.data().dropdown.addItem(item);
   ```
7. Added a data function to grab the data for the dropdown. This will also allow users to grab data based on type.
   ```
   dropdown.data().dropdown.data(); // Returns the entire array of data
   dropdown.data().dropdown.data('{TYPE}'); // Returns an array of data all of type {TYPE}
   ```
8. Added a delItem function to dynamically delete an item from the data list dropdown.
   ```
   dropdown.data().dropdown.delItem(item);
   ```
9. Added a setSelected function to clear and reset the selected items. Expects an array of item IDs that will be the new selected list.
    ```
    let items = ["1", "4"];
    dropdown.data().dropdown.setSelected(items);
    ```
