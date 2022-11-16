# Quarto-mermaid-docx

I'm trying to use mermaid to produce a diagram in html, pdf and docx output. When I use Ctrl Shift B / Render All Formats, I get the following error:

`
ERROR: TypeError: error sending request for url (http://localhost:9222/json/list): error trying to connect: tcp connect error: No connection could be made because the target machine actively refused it. (os error 10061)
`

Regarding the output format:
- If I remove docx from the output in the YML file, the book renders correctly in pdf and html, when I use render all formats. 
- If I remove pdf from the output in the YML file, the book renders correctly in docx and html, when I use render all formats. 
- If I select rendering to MS Word only, the book renders correctly.
- If I select rendering to pdf only, the book renders correctly.

Regarding mermaid:
- If I remove the mermaid diagram, the book renders to all output formats without errors.
- If I wrap the mermaid code in `::: {.content-visible unless-format="docx"} :::` or similar, I still get the error when I try to render to all formats

Version running:
- Quarto 1.2 
- "Elsbeth Geranium" Daily (896a0002, 2022-08-02) for Windows
- R version 4.0.5 (2021-03-31) -- "Shake and Throw"
- Platform: x86_64-w64-mingw32/x64 (64-bit)

The obvious solution for me is not to use the Render All Formats option. But it took me way too long to find out, so I thought this may be helpful to know.

https://github.com/quarto-dev/quarto-cli/issues/3066
