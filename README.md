# cernbox_ui

# Redesigning CERNBox: concept of interaction design

Figma prototype with demonstration of some improvements: https://www.figma.com/proto/It0zUbR8CUiYYJQnTnTO1J/List-operations?node-id=1%3A2&scaling=min-zoom



## 1. List operations

List information and interaction design is the core for whole experience with the application.



| Action                                  | Description                                                                                                                                                                                                                                                                                                                                                | Usability Problem                                                                                                                                                                                                                                           | Possible Improvements                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Comments                                                                            |     |
| --------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- | --- |
| **Select list item**                    | There are 2 selection ways: selecting the checkbox (checkbox-checked: menu with item actions "copy", "move", "delete" appears over the list) and selection by clicking on free space (item highlighted with color: side bar with information about the item appears)   ![](https://codimd.web.cern.ch/uploads/upload_b0b4b2061384e949c0bb40dcd3499199.gif) | Having two different selection ways in one list with 2 results on action leads to a big inconsistency and causes irritation in use (non-expected behavior of interface). Cognitive demanding as the user has to remember which selection causes what result | One way to select items: clicking on item. Result of clicking is color highlighted item with checked checkbox   ![](https://codimd.web.cern.ch/uploads/upload_9752607ea681fde53007c4989d24306e.gif)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                     |     |
| **Deselect item**                       | Selection made with checkbox: deselect by unckecking the checkbox, selection clicking the free space: deselect by closing the sidebar                                                                                                                                                                                                                      | Similar to previous: non-expected, inconsistent bahavior of interface.                                                                                                                                                                                      | Deselect item by clicking the item: checkbox gets unchecked, color highlighting disappears. Another commonly used and known way of deselection is clicking anywhere outside of the list.                                                                                                                                                                                                                                                                                                                                                                                                                           |                                                                                     |     |
| **Select/deselect multiple list items** | Selecting multiple items made by selecting their checkboxes. Selection by clicking the free space of the item is singular.   To deselect user needs to uncheck every checkbox.                                                                                                                                                                             |                                                                                                                                                                                                                                                             | Select multiple items in 3 ways: (1) checking their checkboxes, (2) clicking and dragging your mouse over the items you want to select or (3) by holding down the Shift, Command, or Control key while clicking on items. All 3 ways are well known from using file management operations on OS's, lead to the same result (consistency) and cover different user preferences (also preferences of visually impared users using screenreader). Alternative deselection of all by clicking outside of the list: only 1 click necessary.      ![](https://codimd.web.cern.ch/uploads/upload_2db76cf48d46baaae756efae9d04f3c3.gif)                                                                       |                                                                                     |     |
| **Move item**                           | Move item by selecting it and either clicking "Move" in menu over the list or in the sidebar. It opens a dialog on place of the list, where the user can select the destination folder for moving. After that the user confirms with "move to this folder". After moving the target folder is open istead of the directory from which the item was moved.  | Overall minimum 4 mouse clicks for moving, additional clicks to return back to where the user was. Inefficiency of the interface as well as context loss.                                                                                                   | Moving inside the directory by drag&drop. Popup dialog with possible target folders for moving to other directories (prevents context loss).                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                                                                                     |     |
| **Copy and paste item**                 | To copy an item and paste it, the user selects the item, clicks on "copy" in menu over the list or in the sidebar. Dialog similar to moving opens, the user selects destination folder and confirms.                                                                                                                                                       | Similar to moving: context loss as dialog appears on place of the list. After the action the user finds himself in destination directory of copying. Copying to the same directory with automatic modification of the file name is not possible.            | Better practice is to use a keyboard shortcuts CTRL+C, CTRL+V as well as a popup dialog                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                     |     |
| **Overall actions on single item**      | Actions with the item (copy, move, delete, rename) are placed in the sidebar and over the list when the checkbox is checked.                                                                                                                                                                                                                               | Both placements require leaving the list area and moving the mouse either on top of the screen or to the right side.--> Inefficiency                                                                                                                        | Base actions appear on hover (on focus for screenreader) inside of the list item close to it's name In list visualization on big screens item has a lot of free space to use; bringing actions inside it allows reducing of mouse moving time and 1 mouse click. For more advanced actions a custom context menu on right click can be used (well known interaction) and alternatively a button (...) might be used for users who don't use right click. This way the accessibility of the interface improves as user doesn't have to switch from list to sidebar to call actions, they are attached to each item. ![](https://codimd.web.cern.ch/uploads/upload_1079d15f2d7091db74df85796c235377.gif)|                                                                                     |     |
| **Overall actions on multiple items**   | Actions appear  above the list                                                                                                                                                                                                                                                                                                                             | User needs to move the mouse from item to the top of the list or the sidebar every time he wants to execute the action (inefficiency)                                                                                                                       | Showing important actions (copy, delete, download, share...) inside the list item on hover reduces the mouse movement and creates a mentally better connection of actions to the corresponing item (intuitivity). Other actions can be either shown on right click in a custom context menu or on click of extra button for actions. Popup notifications on executing the actions (e.g. "File copied", "Folder moved to trash") as additional feedback of interface      ![](https://codimd.web.cern.ch/uploads/upload_2db76cf48d46baaae756efae9d04f3c3.gif)                                                                                                                                             |                                                                                     |     |
| **Undo actions**                        | There is no way for quick Undo                                                                                                                                                                                                                                                                                                                             | To Undo e.g. deletion the user needs to go to trash directory and restore it. To undo moving similary: go to destionation directory and move the item back. Inefficiency of the interface                                                                   | Provide Undo functionality with keyboard shortcuts (Pressing Ctrl+Z will undo any change. These shortcuts can also be pressed multiple times to undo or redo multiple changes. Pressing Ctrl+Y would redo the undo. On Apple computers, Command+Z and Command+Y for undo and redo. ![](https://codimd.web.cern.ch/uploads/upload_917bd25fe343cb718a95178cdea89f72.gif)                                                                                                                                                                                                                                                                                                                                 | |     |






_______________________________________________________________

Other design desisions:

### Sidebar

* Sidebar always shown by default (desktop version), can be hidden
* If nothing selected: shows informations about current directory
* If one item selected: metadata of item
* If multiple items selected: metadata of last selected item
* ---> Interface always provides context of object of interest.

### Different views of directory: list, grid

* Similar to list view interactions
* Compact representation
* Concideration of advanced view (for example compact list)
* ---> Covering needs of users with different preferences

_______________________________________________________________


## 2. Sharing



# Sharing Settings

* Call menu by clicking on "share" button that appears on hover or "sharing settings" in the sidebar
* Design desision: Settings in separate modal dialog --> user stays in context, have the option focused, more place for settings, sidebar remains for metadate details





### Shared with me

* Design desision: shares must be accepted or declined before the user can watch the content
* Declined shares can still be accepted
* Accepted shares appear in the list of shares
* Users sees, why the share was shared with him
* For better readability of the list: grouping, filtering...



### Shared by me

* Similar principle to "shared with me"
* * Information about recipients





## Acessibility aspects

There are guidelines for making modern interface elements accessible:

* context menu: extra button to call it as a complement of the right click; https://www.webaccessibility.com/resource-library/platform/?platform=45
* Modal dialogs: https://www.w3.org/TR/wai-aria-practices-1.1/examples/dialog-modal/dialog.html
* hover effect: Tab key selection of element provides the same result as hover
* Infinite scroll vs. pagination
    * Infinite scroll bad for acessibility: https://www.levelaccess.com/infinite-scrolling-impact-on-assistive-technologies-series-1/
    * lots of discussions on usability overall
    * best solution: let the user decide: provide both modes

* ---> Mostly matter of implementation
