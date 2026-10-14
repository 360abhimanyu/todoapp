# Daymark Todo

A small, dependency-free todo app. Tasks are saved in your browser's `localStorage`, so they remain available after you close or reload the page in the same browser profile.

## Open the App

The app is currently available at:

**[http://localhost:4173/index.html](http://localhost:4173/index.html)**

That address works while the local web server is running. To start it again from this project directory, run:

```sh
python3 -m http.server 4173 --bind 0.0.0.0
```

Then open the URL above. Stop the server with `Ctrl+C` in the terminal where it is running. The app is a static page, so it can also be opened directly from `index.html`; using the HTTP URL is more consistent for browser storage.

## Using the Todo List

- Enter a task in the field and choose **Add task** or press Enter.
- Select the circle beside a task to mark it done or active again.
- Use **All**, **Active**, and **Done** to filter the list.
- Choose the × beside a task to delete it.
- Choose **Clear done** to remove every completed task at once.
- The list shows how many tasks remain active. The date at the top uses your browser's locale.

Task text is trimmed before it is saved and can contain up to 240 characters. Empty tasks are not added.

## Data and Privacy

- The app does not use an account, backend, or network service for task data.
- Tasks are stored in this browser's `localStorage` under the key `daymark.tasks.v1`.
- Storage is specific to the browser profile and site origin. Tasks do not automatically sync between browsers or devices.
- Clearing this site's browser storage, using private browsing, or switching browser profiles can make saved tasks unavailable.
- If browser storage is blocked or full, the app displays a status message; it does not upload or back up the list elsewhere.

Each saved task has an ID, its text, and a completed state. The app reads saved values defensively and ignores entries that do not match the expected shape.

## Project Files

- `index.html` contains the page layout, styles, and app logic.
- `README.md` contains these setup and usage notes.

There are no package dependencies or build step.