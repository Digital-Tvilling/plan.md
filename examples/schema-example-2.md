# Schema Metadata
- **Schema Name:** Plan Schema
- **Version:** 1.0.0
- **Last Updated:** 2024-07-03
- **Author:** Your Name
- **Description:** This schema defines the structure and components of a plan for validation purposes.
## Version history

# Custom Data Types

## Predefined Lists

### Status Group Activity
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
- **Email:** String within plan

# Plan Schema

## Plan
- **Name:** String (required)
- **Start Date:** Date (YYYY-MM-DD) (required)
- **End Date:** Date (YYYY-MM-DD) (required)
- **Summary:** String
- **Manager:** Person (required)
- **Objectives:** List of Objective

## Objective
- **Description:** String (required)
- **Status:** Status Group Activity

## Activity
- **Name:** String (required)
- **Start Date:** Date (YYYY-MM-DD) (required)
- **End Date:** Date (YYYY-MM-DD) (required)
- **Status:** Status Group Activity (required)
- **Risk Level:** Risk Level (optional)
- **Assigned To:** Person (optional)
- **Description:** String

## Milestone
- **Name:** String (required, unique)
- **Date:** Date (YYYY-MM-DD) (required)
- **Status:** Status Group Milestone (optional)
- **Description:** String

## Risk
- **Description:** String (required)
- **Impact:** String (required)
- **Mitigation Plan:** String (required)
- **Status:** Status Group Activity (optional)

# Plan Structure
- **Overview:** Plan (required)
- **Objectives:** `List of` Objective
- **Milestones:** `List of` Milestone
- **Activities:** `List of` Activity
- **Risks:** `List of` Risk
 