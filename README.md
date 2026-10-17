# PlanSurf Personal Todos

A lightweight personal task tracker for family responsibilities, errands,
shopping, home tasks, wellbeing, and skills you want to build. Tasks can have a
category, due date, priority, notes, and completion status. Data is saved in
your browser and can optionally sync with the PlanSurf service.

## Use

Open `index.html` in a modern browser. Add tasks, mark them complete, and use
Today, Upcoming, No date, and Completed to focus your list. Export downloads a
JSON backup of your personal tasks.

## Cloud sync

Select **Cloud sync** and sign in with your existing PlanSurf password. The app
uses the fixed PlanSurf cloud service and its existing Daily Spark login and
data endpoints. It saves personal tasks in the `personalTodos` field of the
shared data document, preserving existing Daily Spark task and leave fields.
Cloud sync requires that the service accepts unknown fields on its version 5
Daily Spark document.

The service endpoint is fixed in the app and is not shown in the interface.
Passwords are sent only to the service and are not saved in browser storage.
The returned session token remains in memory until the page is closed or you
sign out.

## Package

The app is a standalone `index.html` page with no build step. Google Fonts and
Lucide icon fonts are loaded from CDNs; the application logic and local storage
do not require a build tool.