# paper_template

A starter template for writing academic papers in LaTeX, with a reproducible
build and automated PDF compilation on every push.

## Layout

```
.
├── paper/
│   ├── main.tex        # the paper
│   ├── refs/
│   │   └── references.bib  # bibliography
│   └── figures/        # figures (PDF/PNG/...)
├── Makefile            # build / clean targets
└── .github/workflows/  # CI that builds the PDF
```

## Building

You need a LaTeX distribution (e.g. TeX Live or MacTeX) with `latexmk`.

```bash
make        # build paper/main.pdf
make clean  # remove build artifacts
```

## Continuous integration

Three GitHub Actions workflows run automatically:

- **build.yml** — compiles the PDF on every push and pull request and uploads
  it as a workflow artifact (also attaches it to tagged releases).
- **build-pdf.yml** — on pushes to `main`, compiles the PDF and publishes it to
  the `pdf` branch.
- **arxiv.yml** — on pushes to `main`, assembles a self-contained arXiv
  submission tarball (source `.tex`, `references.bib`, pre-built `.bbl`, and
  figure PDFs), verifies it compiles standalone, and publishes it to the
  `arxiv` branch.

## License

[MIT](LICENSE)
