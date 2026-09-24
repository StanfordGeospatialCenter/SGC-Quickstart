# Curriculum rules

## Markdown-before-code rule

Every code block in a workshop notebook or lesson should be preceded by a markdown cell that explains:

- the objective of the code block;
- any setup, credentials, or project values the learner must update;
- what the learner should expect the code to do;
- any required files, environment steps, or access checks before running it.

This rule applies to setup cells, authentication steps, imports, data preparation, and any code that depends on a prior notebook or external access.

## Examples

- Before a project ID or authentication cell, explain that users must replace the placeholder value with their own Google Cloud project.
- Before a notebook setup block, describe the libraries being installed and any required access or credentials.
- Before a GeoJSON or AOI step, explain what result the learner is creating and how it will be used in the next stage of the workflow.

## Teaching principle

Students should understand the purpose of each code block before they run it. A short markdown introduction improves clarity, reduces errors, and helps instructors guide learners through a workshop without confusion.
