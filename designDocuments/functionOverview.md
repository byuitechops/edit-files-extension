# Function Overview

## main()

#### Purpose
Serves as the main controller for seeing the user through to the edit window. Holds all pertinent information needed by the other functions.

## extractInfo(url)

#### Purpose
Extracts needed information from the provided URL, such as the OU and domain.

## openFile(filepath)

#### Purpose
Sees the functions for navigating to and opening the requested file through to completion. Holds all pertinent information for those functions to complete their task.

## openManageFiles(domain, ou)

#### Purpose
Opens the given course (as discovered by extractInfo()) to it's "Manage Files" page, in preparation for opening the needed file.

## navigateFileTree(filepath)

#### Purpose
Autonomously navigates the user through to the file requested.

## openEditWindow(filepath)

#### Purpose
Autonomously opens the requested file (once navigated to) into an edit window.

## resizeWindow(window)

#### Purpose
Resizes the edit window to fill the tab.
