# Contributing to Documentation

Making quick fixes to existing text or raising issues is very easy. More complicated changes will require you to set up the [Gitbook toolchain](https://toolchain.gitbook.com/setup.html). If you want to help, [get in touch](../README.md#getting-help).

> **Tip** You will need a [Github](https://github.com/) login to make and submit changes to this guide.

## Overview

This guide is written in [markdown](https://toolchain.gitbook.com/syntax/markdown.html) wiki syntax and stored in the Github [dronecore/docs](https://github.com/dronecore/docs) repo. The book is hosted on [Gitbook.com](https://www.gitbook.com/) and is automatically rebuilt whenever the master branch of the repo is updated. You can also rebuild it locally using the [Gitbook toolchain](https://toolchain.gitbook.com/).

The [API Reference](../api_reference/README.md) section is compiled from source code into markdown using a [separate toolchain](#api-reference) and then copied into Github. Updates to the reference should be made in the [source code repository](https://github.com/dronecore/DroneCore) (see [API Reference](#api-reference) below for more information).

The guide is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) - if you make any changes then they will be made available under the same license. 


## Making a Quick Fix

Simple fixes to an existing page can be made directly on Github:

1. Click the **Edit** button in the top toolbar to open the page

   ![Edit page](../../assets/site/gitbook_toolbar_edit.png)
   
1. Make required changes in the editor section near the top of the page.
2. At the bottom of the page, add a comment and select the second radio button to create a new branch.

   ![Edit page](../../assets/site/github_edit.png)

3. Follow the on-screen instructions to create a pull request with your change.


## Raising an Issue

To raise an issue against the documentation:

1. Open the page with problem content.
1. Click the **Bug** button in the top toolbar.

   ![Raise bug](../../assets/site/gitbook_toolbar_bug.png)
   
   This will open a bug in Github, seeded with the URL/name for the current page. 
1. Enter enough information for someone to understand the problem, and ideally to fix it. 


## Making a Big Change

If you want to make more significant changes or additions to the documentation you will need to set up Git and the gitbook toolchain (this allows you to render the documentation and check that links work). 

For setup information see: [Gitbook toolchain](https://toolchain.gitbook.com/setup.html).


## API Reference

The C++ source code is annotated using comments using [Doxygen](https://www.stack.nl/~dimitri/doxygen/manual/index.html) syntax. You can extract the documentation on Mac OSX or Linux when you [build the library](../contributing/build.md) using the command: 
```
make docs
```

The documentation is then built to: **/install/docs/markdown**. 

> **Tip** At time of writing changes to the API reference are not automatically populated to the Guide.
  Changed markdown files must be manually copied into the Guide's Github repo and submitted. 

<span></span>
> **Note** Extracting the API reference does not work automatically on Windows because the `make` toolchain is different. 

<span></span>
> **Note** *Doxygen* creates xml files from source comments in **/install/docs/xml**. The Python script *generate_markdown_from_doxygen_xml.py* converts these to markdown (and stores in **/install/docs/markdown**).
