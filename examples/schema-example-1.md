# Schema Metadata
- **Schema Name:** ToDo List Schema
- **Version:** 1.0.0
- **Last Updated:** 2024-07-03
- **Author:** Your Name
- **Description:** This schema defines the structure and components of a personal to-do list for validation purposes.
## Version History

# Custom Data Types

## Predefined Lists

### Task Status
- **`Values`:** Not Done, Done
- **`Progressions`:**
  - Not Done -> Done
- **`MD-representations`:** 
 - `- [ ]`: Not Done 
 - `- [x]`: Done

## Objects

# Plan Schema

## ToDo List
- **Name:** String (required)

### Task
- **Description:** String (required)
- **Due Date:** Date (YYYY-MM-DD) (optional)
- **Status:** Task Status (required)

# Plan Structure
- **Overview:** ToDo List (required)
- **Tasks:** `List of` Task (required)
