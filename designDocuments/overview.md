# Edit File Extension

## Problem Description
In Brightspace, there isn't an available API or way to create an intuitive shortcut to editing an html page outside of brightspace. The main purpose of this Chrome Extension is to allow users to right click on any link to an D2L HTML page within a Brightspace course and be provided with an option to "Edit File." When the user clicks this option, the extension navigates to the edit page for that specific file.

## Design Overview
This extension will use Chrome Context Menus to make the new right click option available. Content scripts will be injected into any available brightspace page, as long as they are in a course. Those content scripts will watch for when the user opens the context (right click) menu on a link. If the link's *href* attribute leads to one of the course's html pages, it will add a new option to the context menu. That option will trigger a series of functions housed on the *background.js* background script. Those functions will navigate the user to the correct edit page for the link they selected, by jumping them to the course's "Manage Files" page. Following, it will move them through the necessary folders, then click edit on the appropriate file. This extension will not need to rely on anything aside from jquery. 

Content scripts have access to the DOM of the page they're injected into, which we will need when checking to see what kind of link the user is clicking on. 

The background script continously runs whenever the browser is open, as part of the extension rather than a specific web page. Since navigating to the edit page of a file requires changing pages, using a content script would become difficult. 