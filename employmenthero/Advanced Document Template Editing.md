# Advanced Document Template Editing

## What's included in this document
This document describes the intricacies of the Employment Hero Advanced Document Template Editor from the perspective of whoever might need to modify this document.

## What's not included in this document
This document does not describe processes around how these templates should be issued, and what information needs to be loaded against an employee before (for example) an IEA is issued

## A brief overview of Document Templates in Employment Hero
Document Templates are how documents can be issued to employees. They can be issued ad-hoc via "Bulk Issue Documents" or at the end of the onboarding process.

### Employment hero documentation
Employment Hero has fairly good documentation. These articles touch on Advanced Document Templates:
- [Basic vs Advanced Editor features | HR Comparison](https://help.employmenthero.com/hc/en-au/articles/6483306267919-Basic-vs-Advanced-Editor-features-HR-Comparison)
- [Getting started with the advanced template editor | HR Web Platform](https://help.employmenthero.com/hc/en-nz/articles/6475104802447-Getting-started-with-the-advanced-template-editor-HR-Web-Platform)
- [Using sections in the advanced template editor | HR Web Platform](https://help.employmenthero.com/hc/en-nz/articles/360001226515-Using-sections-in-the-advanced-template-editor-HR-Web-Platform)
- [Using variables in the advanced template editor | HR Web Platform](https://help.employmenthero.com/hc/en-nz/articles/360001226796-Using-variables-in-the-advanced-template-editor-HR-Web-Platform)
- [Using tables in the advanced template editor | HR Web Platform](https://help.employmenthero.com/hc/en-nz/articles/360001225835-Using-tables-in-the-advanced-template-editor-HR-Web-Platform)
- [Using blocks in the advanced template editor | HR Web Platform](https://help.employmenthero.com/hc/en-nz/articles/360001226316-Using-blocks-in-the-advanced-template-editor-HR-Web-Platform)
- [Using the advanced template editor | HR Web Platform](https://help.employmenthero.com/hc/en-nz/articles/360001214836-Using-the-advanced-template-editor-HR-Web-Platform)

## Why editing Advanced Templates is a challange
As part of Employment Hero's implementation they allowed for "building" up to 5 Advanced Templates. We provided our standard Individual Employment Agreement however they made a huge mess of it.

After their attempt at implementing our IEA we found that attempting to tidy up or modify the IEA document template would cause the formatting to break, lots of errors when trying to save changes (around nested blocks).

Tony from Employment Hero communicated that to fully utilize the functionality of the Advanced Template editor, we need to edit the template using the HTML directly.

## The template WYSIWYG editor
![The application template editor](https://github.com/cookbrothersconstruction/documentation/assets/115191984/7c4d8943-98dc-43d7-abe6-fe94dcc80136)

_inserting whitespace at the top or bottom of an existing block_

## Document structure
All content must be in a Block (`<content_block></content_block>`)
All Blocks must be in a Section (`<content_section></content_section>`)
Sections can be optional
_examples_
Blocks can be optional in a group (so that one block must be chosen)
_examples_

### Document format options
_example of the available formatting (normal, heading 1, heading 2, heading 3, heading 4, formatted_

### Content Sections
_options available in editor_

_how this looks in the HTML tag_

### Content Blocks
_options available in editor_

_how this looks in the HTML tag_

### Variables
_what they do_

_limitations_

## Editing in HTML
_whitespace_

### Boilerplate
_the full HTML document container with style_

### Previewing
_previewing this in VSCode_

### Blocks and Sections


### Indentation
_left margins_

## Testing
_caveats around "save and preview"_
_needing to back out, select a different template, back out again, and select the template to test otherwise it won't update_
