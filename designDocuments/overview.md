# Edit File Extension

## Problem Description
In Brightspace, there isn't an available API or way to create an intuitive shortcut to editing an html page. The only two available options are editing a content page by clicking "Edit HTML" after navigating to the page, or selecting the same within the "Manage Files" menu. Both require extra navigation. The main purpose of this Chrome Extension feature is to allow users to right click on any link to an D2L HTML page within a Brightspace course and be provided with an option to "Edit File in Course." When the user clicks this option, the extension navigates to the edit page for that specific file automatically. This used in tandem with the "Course Search" tool will allow users to search for something within a course, and then open directly to the edit page for files in the results.

This feature will be implemented into the existing internal use extension used by the Online Learning department.

## Design Overview
This extension will use Chrome Context Menus to make the new right click option available. The new context menu item will be created in the extension's background script. That option will trigger a series of functions housed on the background script. Those functions will navigate the user to the correct edit page for the link they selected, by jumping them to the course's "Manage Files" page in a new tab. Following, it will move them through the necessary folders, then click "edit" on the appropriate file. Once the edit window has loaded, it will resize it to match the height/width of the current browser window.

The "Edit File in Course" option will be available no matter what website you're on, but only links that match the course link pattern. This pattern includes links in these formats:

*Course Content Page View/Edit*<br>
https://byui.brightspace.com/d2l/le/content/*

*Course Content Quicklinks to View a Content Page*<br>
https://byui.brightspace.com/d2l/common/dialogs/quickLink/quickLink.d2l?ou=*&type=content&rcode=*

https://pathway.brightspace.com/d2l/common/dialogs/quickLink/quickLink.d2l?ou=*&type=content&rcode=*

*Direct Path Address*<br>
https://byui*.brightspace.com/content/enforced/*

https://pathway*.brightspace.com/content/enforced/* (This has not been set up yet)

*Manage Files Download Link*<br>
https://byui.brightspace.com/d2l/common/viewFile.d2lfile/*

https://pathway.brightspace.com/d2l/common/viewFile.d2lfile/*

Note: * Indicates that anything can be placed there in the URL

This feature will not need to rely on anything aside from jquery and native Chrome APIs.

## Data Structure
The only information that the extension needs to store is the location the background script is attempting to navigate the user to. This will be stored solely in the background script, and will be dumped when the user has been successfully navigated to the correct edit page.

## User Interface
No user interface is needed for this project. This extension will not have a popup.

The context menu option will be labeled as "Edit File in Course."

## Structure Chart
---
