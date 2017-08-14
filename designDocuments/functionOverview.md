# Function Overview

## main(info, tab)

Serves as the main controller for seeing the user through to the edit window. Holds all pertinent information needed by the other functions.

Parameters | Details 
--|---
info: Object | Information provided by the contextMenu object, providing the ```.linkUrl``` attribute we need to obtain the link the user selected
tab: Object | Object containing details about the tab where the click took place - not useful for this objective

```javascript
function main(info, tab) {
  // If !extractInfo(info.linkUrl).filepath, then retrieveFilepath(extractInfo(info.linkUrl).ou, extractInfo(info.linkUrl).topicId)
  // Then run openManageFiles(domain, ou, filepath)
}
```

## extractInfo(url)

Extracts needed information from the provided URL, such as the OU and domain. Uses `.split()` to divide up the url.

Parameters | Details 
--|---
url: String | URL string to be used to extract needed information (ou, domain, topicId (if available), filePath (if available))

Returns | Details
--|---
ou: String | Course ID
domain: String | Returns either 'pathway' or 'brightspace' for situations where we need to know
topicId: String | ID of the page we're attempting to edit
filePath: String | Path to the location of the file on the server (if not available, acquired with ```retrieveFilePath```)

```javascript
function extractInfo(url) {
  // url.split('/') --> Get all needed parameters, send them back
}
```

## retrieveFilepath(ou, topicId)

In cases where the provided url does not have the filepath included (`content/enforced/course-name/file-name`), this function will retrieve the filepath via API calls.

Parameters | Details 
--|---
ou: String | Course OU to provide the API with
topicId: String | Topic ID to use to match against API results to find the correct filepath

Returns | Details
--|---
filePath: String | Path to the file on the server: (`content/enforced/course-name/file-name`)

```javascript
function retrieveFilepath(ou, topicId) {
  // Use Josh's API to get list of topicIds from the given OU, then compare to find the file, return it's path
}
```

## openManageFiles(domain, ou)

Opens the given course (as discovered by extractInfo()) to it's "Manage Files" page, in preparation for opening the needed file.

Parameters | Details 
--|---
domain: String | Used to build the URL this function will open (either 'pathway' or 'byui')
ou: String | Course OU used to build the URL this function will open
filePath: String | Used in next function

Returns nothing, but triggers `openFile()`.

```javascript
function openManageFiles(domain, ou) {
  var win = window.open('https://byui.brightspace.com/d2l/lp/manageFiles/main.d2l?ou=65437', '_blank');
  openFile(win, filePath);
}
```

## openFile(win, filePath)

Sees the functions for navigating to and opening the requested file through to completion. Holds all pertinent information for those functions to complete their task.

Parameters | Details 
--|---
win: Window Object | Reference to recently opened Manage Files window
filePath: String | Used in all children functions

Returns nothing; controls sequence to navigate and open file into edit window.

```javascript
function openFile(win, filePath) {
  navigateFileTree(win, filePath);
}
```

## navigateFileTree(win, filePath, callback)

Autonomously navigates the user through to the file requested.

Parameters | Details 
--|---
win: Window Object | Reference to Manage Files window
filepath: String | Contains path to the file this function will navigate to in the Manage Files view
callback: Function | Function to run when we've completed navigating through the system

Returns nothing; navigates to location where file is stored.

```javascript
function navigateFileTree(win, filePath) {
  //var editWindow = ... Reference to newly opened edit window
  openEditWindow(filePath);
}
```

## openEditWindow(filePath)

Autonomously opens the requested file (once navigated to) into an edit window.

Parameters | Details 
--|---
filepath: String | Used to determine the filename when opening the file into the edit window

Returns | Details
--|---
editWindow: Object | Returns object containing information and reference to the newly opened edit window

```javascript
function openEditWindow(filepath) {
  // Sequence of functions here
  // var editWindow = ...reference to newly opened edit window
  resizeWindow(editWindow)
}
```

## resizeWindow(window)

Resizes the edit window to fill the browser tab.

Parameters | Details 
--|---
window: Object | Reference to the edit window just opened, so we can resize it

Returns nothing; resizes edit window.

```javascript
function resizeWindow(window) {
  // Resize the window
}
```

