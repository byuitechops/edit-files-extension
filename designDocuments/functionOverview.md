# Function Overview

## main(info, tab)

Serves as the main controller for seeing the user through to the edit window. Holds all pertinent information needed by the other functions.

Parameters | Details 
--|---
info | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab | Object containing details about the tab where the click took place - not useful for this objective

## extractInfo(url)

Extracts needed information from the provided URL, such as the OU and domain.

Parameters | Details 
--|---
url | URL string to be used to extract needed information (OU, domain, topicID (if available), filepath (if available))

## getFilepath(url)

Extracts needed information from the provided URL, such as the OU and domain.

Parameters | Details 
--|---
url | URL string to be used to extract needed information (OU, domain, topicID (if available), filepath (if available))

## openFile(filepath)

Sees the functions for navigating to and opening the requested file through to completion. Holds all pertinent information for those functions to complete their task.

Parameters | Details 
--|---
info | Details about this
tab | Details about this

## openManageFiles(domain, ou)

Opens the given course (as discovered by extractInfo()) to it's "Manage Files" page, in preparation for opening the needed file.

Parameters | Details 
--|---
info | Details about this
tab | Details about this

## navigateFileTree(filepath)

Autonomously navigates the user through to the file requested.

Parameters | Details 
--|---
info | Details about this
tab | Details about this

## openEditWindow(filepath)

Autonomously opens the requested file (once navigated to) into an edit window.

Parameters | Details 
--|---
info | Details about this
tab | Details about this

## resizeWindow(window)

Resizes the edit window to fill the tab.

Parameters | Details 
--|---
info | Details about this
tab | Details about this

