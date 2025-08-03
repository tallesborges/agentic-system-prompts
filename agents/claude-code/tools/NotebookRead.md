---
source: Production Claude Code CLI tool definition
extracted: 2025-08-03
name: NotebookRead
input_schema:
  type: object
  properties:
    notebook_path:
      type: string
      description: "The absolute path to the Jupyter notebook file to read (must be absolute, not relative)"
    cell_id:
      type: string
      description: "The ID of a specific cell to read. If not provided, all cells will be read."
  required:
    - notebook_path
  additionalProperties: false
  $schema: "http://json-schema.org/draft-07/schema#"
---

Reads a Jupyter notebook (.ipynb file) and returns all of the cells with their outputs. Jupyter notebooks are interactive documents that combine code, text, and visualizations, commonly used for data analysis and scientific computing. The notebook_path parameter must be an absolute path, not a relative path.
