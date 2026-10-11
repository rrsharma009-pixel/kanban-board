# Kanban Board

A fully functional Kanban board with drag-and-drop task management, built with plain HTML, CSS and JavaScript. No backend, external APIs or dependencies are needed.

## Project Overview

Tasks move between four columns: **To Do**, **In Progress**, **Review** and **Done**. The board state is saved in the browser's LocalStorage, so it is still there after a refresh.

## Features

- Drag and drop tasks between columns and reorder them within a column (mouse, touch and pen supported)
- Add, edit and delete tasks with title, description and priority (Low / Medium / High)
- Color-coded priority tags (High: red, Medium: amber, Low: green)
- Task count per column
- LocalStorage persistence
- Responsive layout for desktop and tablet
- Light and dark mode (follows system setting)
- **Bonus:** search bar, priority filter, and due dates with overdue highlighting

## How to Run

No installation is needed.

1. Download or clone this repository.
2. Open `index.html` in any modern browser.

## Project Structure

```
kanban-board/
├── index.html      # markup, styles and JavaScript in one file
├── README.md
└── screenshots/
```

## How It Works

- **State:** all tasks live in one array and each task has `id`, `title`, `desc`, `priority`, `status` and `due`. The board is rendered from this array.
- **Persistence:** every change is saved to LocalStorage under the key `kanban.v1`. On first load, three sample tasks are used.
- **Drag and drop:** built with pointer events instead of the HTML5 drag API, which makes it work on touch devices. While dragging, a floating copy of the card follows the pointer and a dashed placeholder shows where it will land. Pressing Esc cancels a drag.
- **Overdue highlighting:** a task is overdue if its due date is before today and it is not in Done.

## Sample Data

```json
[
  {"id":1, "title":"Design homepage", "desc":"Create wireframes", "priority":"High", "status":"todo"},
  {"id":2, "title":"Setup CI/CD", "desc":"GitHub Actions pipeline", "priority":"Medium", "status":"inprogress"},
  {"id":3, "title":"Write API docs", "desc":"OpenAPI spec", "priority":"Low", "status":"review"}
]
```

## Known Limitations

- Data is stored per browser and device, so it is not synced between devices.
- Clearing the browser's site data removes all tasks.
- Delete uses a simple browser confirmation dialog.
- On narrow screens the columns scroll horizontally rather than stacking.
- Cards cannot be moved with the keyboard alone (use Edit and change the column instead).

## Screenshots

![Board](screenshots/board.png)