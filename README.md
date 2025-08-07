**Project Title**

Wiki Encyclopedia (Completed)

---

## Overview

This project delivers a fully functional Wikipedia–style online encyclopedia built with Django. Users can view, search, create, edit, and navigate randomly among Markdown‑formatted entries, with content rendered dynamically to HTML.

---

## Features Implemented

1. **List Entries**: Homepage displays all entry titles in an alphabetized list.
2. **View Entry**: Visiting `/wiki/<EntryTitle>` renders the corresponding Markdown file as HTML. Unavailable entries show a custom error page.
3. **Search**: Case‑insensitive search returns exact matches or a list of partial matches.
4. **Create Page**: New entries can be created via a form; titles must be unique or an error is shown.
5. **Edit Page**: Existing entries can be edited in a pre‑populated form and saved back to Markdown.
6. **Random Page**: A single click takes users to a randomly selected entry.

---

## Implementation Summary

* **Markdown Handling**: Utilizes `util.get_entry`, `util.save_entry`, and Python-Markdown to convert source files into HTML on the fly.
* **Views**:

  * `index`: Renders homepage with entry list.
  * `entry`: Displays a given page, or error if missing.
  * `search`: Processes search queries, rendering exact or partial results.
  * `new_entry`: Handles form submissions to create new pages.
  * `edit_entry`: Loads existing content for editing and saves updates.
  * `random_entry`: Chooses and redirects to a random page.
* **Templates**: Inherit from `layout.html`, featuring a consistent sidebar (home link, search, create, random) and dynamic content blocks.
* **Forms and Validation**: Django form handling ensures unique titles on creation and proper submission on edits.

---

## Running the Application

1. Activate your virtual environment and install requirements:

   ```bash
   pip install -r requirements.txt
   ```
2. Navigate to the project directory and run migrations:

   ```bash
   python manage.py migrate
   ```
3. Launch the development server:

   ```bash
   python manage.py runserver
   ```
4. Open `http://localhost:8000` in your browser to explore the encyclopedia.

