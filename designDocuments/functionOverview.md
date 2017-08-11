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

## retrieveFilepath(ou, topicId)

In cases where the provided url does not have the filepath included (`content/enforced/course-name/file-name`), this function will retrieve the filepath via API calls.

Parameters | Details 
--|---
ou | Course OU to provide the API with
topicId | Topic ID to use to match against API results to find the correct filepath

## openManageFiles(domain, ou)

Opens the given course (as discovered by extractInfo()) to it's "Manage Files" page, in preparation for opening the needed file.

Parameters | Details 
--|---
domain | Used to build the URL this function will open (either 'pathway' or 'byui')
ou | Course OU used to build the URL this function will open

## openFile(filepath)

Sees the functions for navigating to and opening the requested file through to completion. Holds all pertinent information for those functions to complete their task.

Parameters | Details 
--|---
filepath | Used in all children functions

## navigateFileTree(filepath)

Autonomously navigates the user through to the file requested.

Parameters | Details 
--|---
filepath | Contains path to the file this function will navigate to in the Manage Files view

## openEditWindow(filepath)

Autonomously opens the requested file (once navigated to) into an edit window.

Parameters | Details 
--|---
filepath | Used to determine the filename when opening the file into the edit window

## resizeWindow(window)

Resizes the edit window to fill the tab.

Parameters | Details 
--|---
window | Reference to the edit window just opened, so we can resize it

