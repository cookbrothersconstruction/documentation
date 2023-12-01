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

As part of Employment Hero's implementation they allowed for "building" up to 5 Advanced Templates. We provided our standard Individual Employment Agreement however they made a huge mess of it, and in attempting to fix it, further broke it.

After their attempt at implementing our IEA we found that attempting to tidy up or modify the IEA document template would cause the formatting to break, lots of errors when trying to save changes (around nested blocks), and entire sections of content disappearing or moving to random other places in the document.

Tony from Employment Hero communicated that to fully utilize the functionality of the Advanced Template editor, we need to edit the template using the HTML directly. The bulk of this document explains how to do that correctly.

## The template WYSIWYG editor

This is how the actual template editor looks:

![The application template editor](https://github.com/cookbrothersconstruction/documentation/assets/115191984/7c4d8943-98dc-43d7-abe6-fe94dcc80136)

It's recommended not to use this editor, and instead edit the HTML outside of the platform.
The master (original at the time of implementation) IEA document template which can be inserted as HTML directly into the HTML editor is available here, alongside the same master inside HTML document boilerplate for previewing outside the platform (see below).

## Document structure

All content must be in a Block (`<content_block></content_block>`)
All Blocks must be in a Section (`<content_section></content_section>`)

Sections can be marked as optional (have the section or don't have the section). Here's how that looks when issuing a document:

![Optional Sections](https://github.com/cookbrothersconstruction/documentation/assets/115191984/cd06ccb1-f3f9-4887-a2eb-9f73b9946336)


Blocks can be optional in a group (so that one block must be chosen). Here's how that looks when issuing a document:

![Optional Blocks](https://github.com/cookbrothersconstruction/documentation/assets/115191984/119233b1-29ba-4da8-9c9a-5a7650774f9d)

When issuing a Document Template the application will warn you if you have not removed an optional block provided it's grouped with at least one other:

![Required Optional Block](https://github.com/cookbrothersconstruction/documentation/assets/115191984/874d835f-2f91-4b35-88b7-acbbd2824e2d)


### Document format options

The editor itself allows for the following formatting styles, which match to the indicated HTML element **in the editor**:
- Normal (`<p></p>`)
- Heading 1 (`<h1></h1>`)
- Heading 2 (`<h2></h2>`)
- Heading 3 (`<h3></h3>`)
- Heading 4 (`<h4></h4>`)
- Formatted (`<pre></pre>`)

In the document output (the completed template which the employee will see) headings are transformed to `<span></span>` tags and look like this:

![Formatting options output](https://github.com/cookbrothersconstruction/documentation/assets/115191984/87240798-4c45-43b0-8fad-a80533689237)


### Content Sections

Content Sections can accept the following options within the editor:

![Content Section options in the editor](https://github.com/cookbrothersconstruction/documentation/assets/115191984/c13fa702-aa0b-4d77-b130-3ec0acced690)

Which maps to the following HTML:

`<contract_section hide_title="true" hide_title_in_document="true" id="18896547" is_show="true" optional="true" premium="false" title="Appendix 6 - Carp / LH">`

### Content Blocks

Content Blocks can accept the following options within the editor:

![Content Block options in the editor](https://github.com/cookbrothersconstruction/documentation/assets/115191984/20f2d7b4-4092-451c-a56a-539a465d4789)

Which maps to the following HTML:

`<contract_block block_group="Uniform Site / Office" id="53167791" optional="true" probation="false" visible="true">`

### Variables
_what they do_
Best to insert inside the editor, as they may need an id attribute

_limitations_
You can't apply styling to variables themselves, meaning they may not always look right in context.

## Editing in HTML
_whitespace_

### Composing Blocks and Sections

leaving ids empty and copying the content back out after the editor to receive IDs

### Other accepted content

You can also add other types of HTML content such as:
- `<ul>`
- `<ol>`
- `<div>`
- `<strong>`
- `<u>`
- `<br />`
- potentially others

**You can not include JavaScript**

**You can include inline CSS but not CSS style blocks**

### Boilerplate

In order to preview the Document Template outside the platform it's beneficial to wrap the template HTML content in a boilerplate document which can contain a style block so that when previewing you can see where the Blocks and Sections are:

![Previewing the Document Template inside boilerplate](https://github.com/cookbrothersconstruction/documentation/assets/115191984/5f158319-79e0-426a-92af-30b5092275f5)

This was done in VSCode and the HTML Preview extension.

### Additional styling (which is used within the IEA template)

**Links**
Links within the HTML will work fine, and you can include the `target="_blank"` attribute so the link opens in a new tab (recommended).

**Tables**
Tables can be used to format content, just beware that you will need to end the table and start a new one if you want Content Blocks or Content Sections to _appear_ inside a table.

**Indentation using left margins**
Indending is done using a style attribute `margin-left: 20px`, additional indentation is achieved by incrementing this by `10` at a time

**Text colouring**
This is possible but not recommended for printing / reading / accessibility reasons

**Centering**
Centering is achieved using a style attribute `style="text-align: center;"`

**Underlining**
Underlining is achieved using `<u></u>` tags

Special characters
`&nbsp;`
`&rsquo`
`&ndash`


## Testing

The templates are non-trivial to test.
You can "Save and Preview" from the editor, but you can't test the blocks themselves there so you'll need to (bulk) issue the document so see how the final copy (received by the employee) will look.

When issuing the document and selecting the template, if you've made changes to the template then you will need to select any other template, then go back and select the template you want to test. Employment Hero somewhat saves it's state even between browser sessions in this way.


## BE CAREFUL

As this module of the system is very fragile you should ensure that:

- You don't change and always keep the original master template from implementation
- Clone an existing template in the system before making modifications
