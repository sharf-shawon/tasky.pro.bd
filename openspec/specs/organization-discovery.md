# Capability: Organization & Discovery

Tools for searching, sorting, and filtering tasks and lists.

## User Stories

- As a user, I want to search for specific tasks or list titles.
- As a user, I want to sort my lists by different criteria (alphabetical, age, completion).
- As a user, I want to filter my lists to see only those that are empty, completed, or have open tasks.

## Functional Requirements

- **Search**:
    - Real-time search that matches list titles and task items.
    - Highlight matching text in list titles and task items.
    - Show only lists that contain a match.
- **Sorting**:
    - Default (manual) order.
    - Alphabetical (A-Z and Z-A).
    - Chronological (Newest and Oldest).
    - By size (Most items).
    - By progress (Most complete).
- **Filtering**:
    - All lists (no filter).
    - Lists with incomplete tasks.
    - Fully completed lists.
    - Empty lists.

## UI/UX

- Integrated search bar in the toolbar.
- Dropdown for sorting.
- Cycle button for filtering.
- Visual feedback on the number of results found.
