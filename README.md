# BRAC University Presentation Template (LaTeX Beamer)

A clean, ready-to-use **BRACU presentation template** for a thesis defence, a seminar or a
conference talk at BRAC University. Written in LaTeX Beamer, in the university's colours,
with one file per section and a working bibliography.

**[→ Open the Overleaf project](https://www.overleaf.com/read/zpygvzwcgdxw#ce8602)**
— read-only; use **Menu → Copy Project** to get your own editable copy.

**[→ Or import this repository straight into Overleaf](https://www.overleaf.com/docs?snip_uri=https://github.com/prasenjit9619/bracu-presentation-template/archive/refs/heads/main.zip&engine=pdflatex)**
— one click, no download, compiler already set to pdfLaTeX.

![compiler: pdfLaTeX](https://img.shields.io/badge/compiler-pdfLaTeX-blue)
![licence: MIT](https://img.shields.io/badge/licence-MIT-green)
![Overleaf ready](https://img.shields.io/badge/Overleaf-ready-47A141)

---

## Why this one

Most university Beamer templates are either a single 400-line `main.tex` that becomes
unmanageable by the third rehearsal, or so heavily styled that changing anything breaks the
layout. This one is deliberately plain:

- **One file per section.** Add `files/05_future_work.tex`, `\input` it, done. Two people
  can edit different sections without a merge conflict.
- **Colours in one place.** Three hex values at the top of `config.tex`. Change them and
  the whole deck follows — including if you are not at BRAC University and want your own
  institution's colours.
- **A bibliography that already works.** `ref.bib` is wired up; `\cite{key}` just works.
- **It compiles as-is.** Clone it, hit recompile, and you get a real example deck. You can
  see what each piece does before you change anything.

## Getting started

### In Overleaf (easiest)

Two routes, both free.

Open the **[live Overleaf project](https://www.overleaf.com/read/zpygvzwcgdxw#ce8602)** and
choose **Menu → Copy Project**. You get an editable copy in your own account, exactly as
the author maintains it.

Or **[import this repository](https://www.overleaf.com/docs?snip_uri=https://github.com/prasenjit9619/bracu-presentation-template/archive/refs/heads/main.zip&engine=pdflatex)**
directly from GitHub, which always pulls the latest commit and arrives with the compiler
already set to pdfLaTeX.

If you would rather do it by hand: download this repository as a ZIP, then in Overleaf
choose **New Project → Upload Project**, set the compiler to **pdfLaTeX** under
**Menu → Compiler**, and make `main.tex` the main document.

### Locally

With TeX Live or MacTeX installed:

```bash
git clone https://github.com/prasenjit9619/bracu-presentation-template.git
cd bracu-presentation-template
latexmk -pdf main.tex
```

## What is where

| File | Purpose |
|---|---|
| `main.tex` | Title, author, supervisor, and the list of sections. **Start here.** |
| `config.tex` | Packages, colours, and the institute block on the title slide. |
| `files/` | One `.tex` per section. Add a file, then `\input` it in `main.tex`. |
| `img/` | The logo and your figures. |
| `ref.bib` | References, cited with `\cite{key}`. |
| `LICENSE` | MIT. Use it for anything, including commercially. |

## Making it yours

1. **Title and author** — top of `main.tex`. Replace the supervisor line or delete it.
2. **Colours** — three `\definecolor` lines in `config.tex`. If you are at another
   university, sample your logo with any image editor's colour picker rather than guessing.
3. **Logo** — replace `img/bracu_logo.png`, keeping roughly the same aspect ratio.
4. **Sections** — one file each under `files/`, `\input` in the order you want them.

One warning worth knowing in advance: Beamer's Madrid theme draws the title on a coloured
panel, so if you set the title foreground to the same colour as that panel you get an
invisible title. If your title vanishes, that is why.

## A note on slide overflow

Beamer does not warn you loudly when a slide runs past the bottom edge — it just quietly
clips or spills. After compiling, check the log:

```bash
grep -c "Overfull \\\\vbox" main.log
```

Zero is what you want. If it is not zero, cut a bullet or set that frame `\small`. Avoid
`allowframebreaks` on content slides: it silently splits one slide into "I", "II", "III",
and your audience sees the same title three times.

## Frequently asked

**Does this work for a BRACU thesis defence?** Yes — that is what it was built for. The
section skeleton (introduction, methodology, results, conclusion) matches the usual defence
structure, and the bibliography handles the citation load.

**Can I use it if I am not at BRAC University?** Yes. Swap the logo and the three colours
and nothing else assumes BRACU.

**Which compiler?** pdfLaTeX. XeLaTeX and LuaLaTeX also work if you prefer them, but the
fonts are set up for pdfLaTeX.

**Can I use it for coursework, a journal talk, or a job seminar?** Yes. MIT licence, no
attribution required — though a star is welcome.

## Contributing

Issues and pull requests are welcome, particularly fixes for anything that breaks in a
current TeX Live, and Bangla-language support if someone wants to add it.

## Credits

This template is a thin layer over other people's work, and it is worth being precise
about whose.

**Beamer and the Madrid theme** are by **Till Tantau**, who created Beamer and wrote the
Madrid theme in 2007; Beamer is now maintained by Joseph Wright, Vedran Miletić and
contributors. Everything that makes these slides look like Beamer slides — the structure,
the navigation, the colour themes beneath Madrid — is theirs. Beamer is distributed under
the LaTeX Project Public License and the GNU GPL, and is not redistributed here: this
repository only contains a document that loads it.

What is added here is modest by comparison: BRAC University's colours and logo, the
institute block, the split of sections into one file each, a wired-up bibliography, and
documentation.

## Licence

MIT — see [LICENSE](LICENSE). Free to use, modify and redistribute, including for
commercial purposes.

---

*Keywords: BRAC University presentation template, BRACU Beamer template, BRAC University
thesis defence slides, LaTeX presentation template Bangladesh, BRACU thesis presentation,
Beamer template for university defence, Overleaf BRAC University template.*
