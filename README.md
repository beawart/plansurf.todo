# PlanSurf Personal Reminders

A friendly personal reminder list for family responsibilities, errands,
shopping, home tasks, wellbeing, and skills you want to build. Reminders can
have a category, a date, priority, notes, and completion status. Dates are
gentle prompts, not deadlines: unfinished reminders stay on your list without
being marked overdue. Data is saved in your browser and can optionally sync
with the PlanSurf service.

## Use

Open `index.html` in a modern browser. Add reminders, mark them complete, and
use Reminders, Coming up, No date, and Completed to focus your list. Export
downloads a JSON backup of your personal reminders.

## Cloud sync

Select **Cloud sync** and sign in with your existing PlanSurf password. The app
uses the PlanSurf service's separate `todo` app routes. The service maps that
app key to `plansurf.todo-data.json` in the private data repository, so todo
sync reads and writes its own file and does not modify Daily Spark data. If the
file does not exist yet, the service returns an empty object; the first cloud
save creates the todo document.

If you create the file manually first, initialize it as:

```json
{
	"app": "plansurf-todo",
	"version": 1,
	"tasks": [],
	"deletedTaskIds": []
}
```

Deleted task IDs are retained so a later cloud sync does not restore removed
tasks.

The service endpoint is fixed in the app and is not shown in the interface.
Passwords are sent only to the service and are not saved in browser storage.
The returned session token remains in memory until the page is closed or you
sign out.

## Package

The app is a standalone `index.html` page with no build step. Google Fonts and
Lucide icon fonts are loaded from CDNs; the application logic and local storage
do not require a build tool.