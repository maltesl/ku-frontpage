# ku-frontpage

A LaTeX package for use at University of Copenhagen.

Intended to create a titlepage that resembles as closely as possible the official design for Master projects and PhD theses.
The Microsoft Word templates can be found at https://designguide.ku.dk/.

## Installation

Just copy the `ku-frontpage.sty` and the `logos` folder into your current working directory.
You can then include the package with for example:

```latex
\usepackage[english, science]{ku-frontpage}
```

## Options

##### Options when including the package

Name                  | Available options               | Default     | Notes
---                   | ---                             | ---         | ---
Language              | `english`, `danish`             | `english`   |
Faculty               | `science`, `sund`, `samf`, `ku` | `science`   | Will change the logo and text at the top of the page accordingly.
Hyperref?             | `hyperref`                      |             | Enables the hyperref package and sets default.
Drop caps?            | `dropcaps`                      |             | Will allow you to include drop caps with `\lettrine{D}{rop caps}`.
Submission statement? | `submissionstatement`           |             | Adds the mandatory statment "This thesis has been submitted [...]" for PhD theses

##### Commands for changing the text

Name                         | Function                                                                                      | Example
---                          | ---                                                                                           | ---
`\author{...}`               | Sets the author.                                                                              | `\author{Mads Ohm Larsen}`
`\title{...}`                | Sets the title of the document.                                                               | `\title{Quasicrystal Simulation}`
`\subtitle{...}`             | Sets the subtitle of the document.                                                            | `\subtitle{An investigation}`
`\date{...}`                 | Sets the date of the document.                                                                | `\date{Handed in: \today}`
`\frontpageauthor{...}`      | Sets the author for the frontpage, only needed as a workaround, see known issues below.       | `\frontpageauthor{Mads Ohm Larsen}`
`\frontpagetitle{...}`       | Sets the title for the frontpage, only needed as a workaround, see known issues below.        | `\frontpagetitle{Quasicrystal Simulation}`
`\frontpagesubtitle{...}`    | Sets the subtitle for the frontpage, only needed as a workaround, see known issues below.     | `\frontpagesubtitle{An investigation}`
`\frontpagedate{...}`        | Sets the date for the frontpage, only needed as a workaround, see known issues below.         | `\frontpagedate{Handed in: \today}`
`\assignment{...}`           | Sets the assignment type.                                                                     | `\assignment{PhD thesis}`
`\advisor{...}`              | Sets the advisor.                                                                             | `\advisor{Advisor: Anders Andersen}`
`\frontpageimage{...}`       | Sets the image for the titlepage                                                              | `\frontpageimage{example.png}`
`\kupdfsetup{...}{...}{...}` | Sets various information in the result PDF. Requires the `hyperref` option.                   | `\kupdfsetup{My title}{My subject}{My name}`
`\submissionstatement{}`     | Sets custom text to be used at the bottom of the titlepage                                    | `\submissionstatement{This thesis has been submitted elsewhere}`

You can disable a command, by setting it to nothing, for example if you do not want a subtitle, you can use `\subtitle{}`.

For SUND and SCIENCE the submission statements required as of 2021-04 are
automatically set, but you can still override them with `\submissionstatement{}`.

Three colors are also defined as well as a setting for current color.
These are `KU`, `KUsund`, and `KUscience`.
Using `\KUCOLOR` will give you the KU color.

## Known issues

`ku-frontpage` patches commands such as `\author` to extract the information
needed for the frontpage. This fails for some combinations of LaTeX
distributions and document classes (for example the `memoir` class). If
patching fails, a warning message in the compilation log will point this out as
well as what to do; An alternative command to set e.g. the author for the
frontpage will be provided, prefixed with `frontpage`, so for example
`\frontpageauthor`. You will still need to use the usual `\author` command
provided by the document class.

## Fonts

You may want to use a different font for the titlepage. In this case, you can
use something like in the following example:
```
\begingroup
  \fontencoding{T1}\fontfamily{LinuxLibertineT-OsF}\selectfont
  \maketitle
\endgroup
```
Replace `LinuxLibertineT-OsF` by the font of your choice.

## Examples

The file `example.tex` contains an example.

## Legal

The UCPH logo is protected by a European patent.
The files in the logos folder can be freely distributed and used as part of the ku-frontpage project by current/former students at UCPH in connection with UCPH projects.

For more information go to [the official design guide](http://designguide.ku.dk/om_design/varemaerkebeskyttelse/).

---

Copyright 2021 Mads Ohm Larsen

Copyright 2021 Malte Leip <malte@leip.net>

The package is distributed under the terms of the MIT License:

---

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
