# Schema Metadata
- **Schema Name:** Plan Schema
- **Version:** 1.0.0
- **Last Updated:** 2024-07-03
- **Author:** Your Name
- **Description:** This schema defines the structure and components of a plan for validation purposes.

## Version history

# Custom Data Types

## Predefined Lists

### Status Group Task
- **`Values`:** Not Started, In Progress, Completed
- **`Progressions:`**
  - Not Started -> In Progress
  - In Progress -> Completed

### Status Group Milestone
- **`Values:`** Pending, Completed
- **`Progressions:`**
  - Pending -> Completed

### Risk Level
- **`Values`:** Low, Medium, High
- **`Progressions`:**
  - Low -> Medium
  - Medium -> High

## Objects

### Person
- **Name:** String
- **Email:** String (unique within plan)

### Phase
- **Name:** String (required, unique within plan)
- **Start Date:** Date (YYYY-MM-DD) (required)
- **End Date:** Date (YYYY-MM-DD) (required)

# Plan Schema

## Plan
- **Name:** String (required, unique within plan)
- **Start Date:** Date (YYYY-MM-DD) (required)
- **End Date:** Date (YYYY-MM-DD) (required)
- **Summary:** String
- **Manager:** Person (required)
- **Phases:** `List of` Phase (required)

## Objective
- **Description:** String (required)
- **Status:** Status Group Task
- **Phase:** Phase (required)

## Task
- **Name:** String (required, unique within tasks)
- **Start Date:** Date (YYYY-MM-DD) (required)
- **End Date:** Date (YYYY-MM-DD) (required)
- **Status:** Status Group Task (required)
- **Risk Level:** Risk Level (optional)
- **Assigned To:** Person (optional)
- **Description:** String
- **Phase:** Phase (required)

## Deliverable
- **Name:** String (required, unique within deliverables)
- **Due Date:** Date (YYYY-MM-DD) (required)
- **Description:** String
- **Phase:** Phase (required)

## Milestone
- **Name:** String (required, unique within milestones)
- **Date:** Date (YYYY-MM-DD) (required)
- **Status:** Status Group Milestone (optional)
- **Description:** String
- **Phase:** Phase (required)

## Risk
- **Description:** String (required, unique within risks)
- **Impact:** String (required)
- **Mitigation Plan:** String (required)
- **Status:** Status Group Task (optional)
- **Phase:** Phase (required)

# Plan Structure
- **Overview:** Plan (required)
- **Objectives:** `List of` Objective
- **Tasks:** `List of` Task
- **Deliverables:** `List of` Deliverable
- **Milestones:** `List of` Milestone
- **Risks:** `List of` Risk
