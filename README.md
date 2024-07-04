# plan.md

## Introduction
Welcome to `plan.md` – a neat way (for some...) to formulate plans using Markdown and schemas. 

## What it is

The basic idea is to define some standards in how plans, in general, can be formulated in Markdown using standard Markdown syntax and using a schema to show which kind of structures and entities are expected in the plan.

Why do this:
- **Files/text first:** Keep/convert your plans in plain text files for easy access and management.
- **Simplicity:** Using Markdown makes creating and reading plans easy and enjoyable. Especially using LLMs. 
- **Extendability:** Easily extend and customize your plans as needed.
- **Flexibility:** Customize schemas to fit any type of plan – from project management to personal to-do lists.
- **Collaboration:** Markdown is great for collaboration, making it simple to share and edit plans with others.
- **Interoperability:** `plan.md` allows multiple different plan structures to co-exist. 

## What it is not

A visualization libary or software application. 

## Todo
The work is a bit experimental and still in development and feedback is very welcome. Feedback and issues are handled as issues. 

# File Types

## Schema Files
Schema files define the structure, components, and validation rules of a plan. They are used to ensure consistency and accuracy in the creation of plan files.

## Plan Files
Plan files are instances that follow the defined schema. They contain specific details and data structured according to the schema.

# General Format

## Schema Metadata
Each schema file has the following overall structure:
```markdown
# Schema Metadata

- **Schema Name:** The name of the schema.
- **Version:** The version of the schema.
- **Last Updated:** The date when the schema was last updated.
- **Author:** The author of the schema.
- **Description:** A brief description of the schema's purpose.

## Version History
Version history of the schema

## Custom Data Types
Define any custom data types, including predefined lists and objects, used within the schema.

### Predefined Lists
Lists of predefined values. Can also contain progression rules and MD-representations.

### Objects
Definitions of complex data types with their attributes.

## Plan Schema
The core structure of the schema, detailing the main components and their attributes.

## Plan Structure
A summary of the key components that must be included in plan files, following the defined schema.

```

## Reserved terms

Reserved terms are written `like this` and carries specific meaning in the schema. The currently reserved words are: 
* `Values`: A set of values for a Predefined List
* `Progressions`: If there is a sequence in which the Predefined List should progress
* `MD-representations`: Key-value pairs for a Predefined List, e.g. "`- [ ]`: Not Done "
* `List of`: Used in Schema definition to show that one component can contain a list of other components 

For types the following terms can be used as paramthesis:
* (unique): 
* (unique within plan): 
* (required): 
* (optinal): 

## Basic Types
The basic types supported in the schema are:
- **String:** Used for any text data, including names, descriptions, and identifiers.
- **Number:** Used for any numerical data. When you need specific numerical types, you can distinguish between Integer and Float.
- **Boolean:** Useful for binary true/false conditions.
- **Date/Time/DateTime:** Use these types to represent temporal data. They ensure that dates and times are formatted consistently.
- **Array/List:** Use these to represent collections of data. The items in the array can be of any type, including complex objects.

# Usage
1. **Define a Schema:** Create a schema file that outlines the structure and validation rules for your plan.
2. **Create a Plan:** Based on the schema, create a plan file that includes specific details and data.
3. **Validation:** Ensure that the plan file adheres to the structure and rules defined in the schema for consistency and accuracy.

This guide should help you create and manage schema and plan files effectively, ensuring that your plans are structured and validated properly.


# Examples
## Simple
### todo-list.md

```markdown
# ToDo List

Based on schema [todo-schema.md](todo-schema.md).

## Overview
- **Name:** My Daily To-Do List
- **Owner:** John Doe (john.doe@example.com)

## Tasks
- **Description:** Buy groceries
- **Due Date:** 2024-07-04
- **Status:** Not Done

- **Description:** Finish report
- **Due Date:** 2024-07-03
- **Status:** Done

- **Description:** Call plumber
- **Due Date:** 2024-07-05
- **Status:** Not Done

- **Description:** Workout
- **Due Date:** 2024-07-03
- **Status:** Done

- **Description:** Read a book
- **Due Date:** 2024-07-04
- **Status:** Not Done
```


### todo-list-schema.md

```markdown
# Schema Metadata
- **Schema Name:** ToDo List Schema
- **Version:** 1.0.0
- **Last Updated:** 2024-07-03
- **Author:** Your Name
- **Description:** This schema defines the structure and components of a personal to-do list for validation purposes.
## Version history

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
- **Tasks:** `List of` Task

### Task
- **Description:** String (required)
- **Due Date:** Date (YYYY-MM-DD) (optional)
- **Status:** Task Status (required)

# Plan Structure
- **Overview:** ToDo List (required)
- **Tasks:** `List of` Task (required)

```
## Other examples
See 

* Very simple example:  [[example-plan-1]] and [[schema-example-1]]
* A bit more formal plan: [[example-plan-2]] and [[schema-example-2]]
* Even more formal plan: [[example-plan-3]] and [[schema-example-3]] 