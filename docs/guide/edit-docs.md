# Come usare la documentazione

Tutorial on how to edit, name and organize pages in this documentation repository to share knowledge and ensure clear communication and informations on subsystem functionality.

---

## Editing documents

1. **Locate the file**
   The documentation root is the `docs/` directory
   - `index.md` is the main homepage. It's the page you see rendered on [`docs.redpropulsion.it`](docs.redpropulsion.it)
   - The folder structure reflects the pages in the website
     - e.g. `hw/asterics/pwr.md` it's equivalent to navigate to [`docs.redpropulsion.it/hw/asterics/pwr`](/hw/asterics/pwr.md)

2. **Edit the content**
   Open the file in your favourite text editor and apply the changes you need. Use markdown syntax for formatting. We are using mkdocs-material as the theme engine for the docs, it adds many features over the plain mkdocs, so **please** refer to its docs to better use it

3. **Preview changes**
   You can preview the changes to the documentation by serving the webserver locally by doing `mkdocs serve` and then going to the local webserver hosted (typically) on port `8000`

---

## Adding new documents

1. Create the file (with `.md` format) in the appropiate directory and with a descriptive name.
2. Save, e.g. we just created a new doc called `new-board.md` in the `docs/hw/` folder.
3. Update the navigation configuration
   open the `mkdocs.yml` and go in the `nav` section.

   ```yaml
   nav:
    - Hardware:
        - Overview: hw/index.md
        - Nuova scheda: hw/new-board.md
   ```

4. If the documentation needs it, you may also have to update (or add) the references to that page in the index or parent page to be able to reach it more efficiently

---

## Adding media

To add media use the `assets` folder to upload images and reference them in your code.

---

## Naming Convention

!!! note
TODO: do be determined

- File names:
  all lowercase letters and spaces must be repplaced with dashes `-`

- Headings:
  This follows the markdown specs: only one header per page as the main title (`#`) and `##` or `###` for subsections.

## Markdown Features and Extensions

This repository supports advanced Markdown features. Use the following extensions for better formatting:

1. **Admonitions**:
   Add notes, warnings, or tips:
   ```markdown
   !!! note
       This is a note.
   !!! warning
       This is a warning.
   ```

2. **Collapsible Sections**:
   Use collapsible sections for detailed content:
   ```markdown
   ??? info "Click to expand"
       Detailed information goes here.
   ```

3. **Mermaid Diagrams**:
   Add diagrams for workflows or architecture:
   ```mermaid
   graph TD;
       A-->B;
       B-->C;
   ```

4. **Tabbed Content**:
   Use tabs for alternative views:
   ```markdown
   === "Option 1"
       Content for option 1.
   === "Option 2"
       Content for option 2.
   ```

---

## Publishing changes

Create a commit with an appropiate title to describe what you edited/added/deleted and push it to remote. The [runner](../runner/config_runner.md) will take care of the rest and automagically publish the changes in a few seconds.
