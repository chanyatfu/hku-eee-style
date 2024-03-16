## Kickstart
1. Install the LaTeX Workshop extension in your Visual Studio Code.
2. Copy and paste the following setting in you `setting.json` file (open it by `cmd + ,`).
3. Run `xe * 2` if you don't need citation, run `xelatex -> makeindex -> bibtex -> xelatex*2` if you need citation.

## LaTeX Workshop Setting
```
  "latex-workshop.latex.recipes": [
    {
      "name": "xe*2",
      "tools": ["xelatex", "xelatex"]
    },
    {
      "name": "xelatex -> bibtex -> xelatex*2",
      "tools": ["xelatex", "bibtex", "xelatex", "xelatex"]
    },
    {
      "name": "xelatex -> makeindex -> bibtex -> xelatex*2",
      "tools": ["xelatex", "makeindex", "bibtex", "xelatex", "xelatex"]
    },
    {
      "name": "xelatex",
      "tools": ["xelatex"]
    }
  ],
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk"
  ],
  "latex-workshop.latex.tools": [
    {
      "name": "latexmk",
      "command": "latexmk",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "%DOC%"
      ]
    },
    {
      "name": "xelatex",
      "command": "xelatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        // "-output-directory=%DIR%/output",
        "%DOC%"
      ]
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": ["%DOCFILE%"]
    },
    {
      "name": "clean",
      "command": "rm",
      "args": ["*.bbl"]
    },
    {
      "name": "latexindent",
      "command": "latexindent",
      "args": ["--silent", "--overwrite", "%DOC%"]
    },
    {
      "name": "makeindex",
      "command": "makeindex",
      "args": ["%DOCFILE%.nlo", "-s", "nomencl.ist", "-o", "%DOCFILE%.nls"]
    }
  ],
```

## VSCode Ignore setting
```
  "files.exclude": {
    "**/*.aux": true,
    "**/*.synctex.gz": true,
    "**/*.synctex(busy)": true,
    "**/*indent.log": true,
    "**/*.out": true,
    "**/*.bbl": true,
    "**/*.blg": true,
    "**/*.lot": true,
    "**/*.lof": true,
    "**/*.toc": true,
    "**/*.ilg": true,
    "**/*.nlo": true,
    "**/*.nls": true
  },
```
