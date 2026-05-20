# Capability: Task Management

Core task and list management functionality for Tasky.

## User Stories

- As a user, I want to create multiple lists to organize different types of tasks.
- As a user, I want to add, edit, and delete items within a list.
- As a user, I want to mark items as completed to track my progress.
- As a user, I want to clone a list to quickly create a similar one.
- As a user, I want to reorder items within a list or move them between lists using drag and drop.

## Functional Requirements

- **List Operations**:
    - Create a new list with a default title.
    - Edit list title.
    - Delete a list with a confirmation modal.
    - Clone a list (including all items).
- **Item Operations**:
    - Add a new item to a list via an input field.
    - Edit item text in a multi-line textarea that auto-resizes.
    - Toggle item completion status.
    - Delete an item.
- **Organization**:
    - Drag and drop items to reorder them within a list.
    - Drag and drop items to move them to a different list.
- **Progress Tracking**:
    - Visual progress bar for each list showing the percentage of completed tasks.
    - Meta information showing the number of items and completed status.

## Non-Functional Requirements

- **Performance**: UI updates should be snappy and use `requestAnimationFrame` for DOM heavy operations.
- **XSS Protection**: All user-generated content must be escaped before being rendered.
- **Accessibility**: Support keyboard shortcuts (Enter to add/blur, Backspace to delete empty items).

## UI/UX

- Modern dark theme with accent colors for primary actions.
- Responsive grid layout for lists.
- Empty states for when no lists are present.
- Toast notifications for confirming actions.
