# Function Overview

## main(info, tab)

Serves as the main controller for seeing the user through to the edit window. Holds all pertinent information needed by the other functions.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details of the tab where the click took place - not needed for this objective

## extractInfo(url)

Extracts needed information from the provided URL, such as the OU and domain.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details of the tab where the click took place - not needed for this objective


## openFile(filepath)

Sees the functions for navigating to and opening the requested file through to completion. Holds all pertinent information for those functions to complete their task.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details of the tab where the click took place - not needed for this objective


## openManageFiles(domain, ou)

Opens the given course (as discovered by extractInfo()) to it's "Manage Files" page, in preparation for opening the needed file.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details of the tab where the click took place - not needed for this objective


## navigateFileTree(filepath)

Autonomously navigates the user through to the file requested.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details of the tab where the click took place - not needed for this objective


## openEditWindow(filepath)

Autonomously opens the requested file (once navigated to) into an edit window.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details of the tab where the click took place - not needed for this objective


## resizeWindow(window)

Resizes the edit window to fill the tab.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details of the tab where the click took place - not needed for this objective

