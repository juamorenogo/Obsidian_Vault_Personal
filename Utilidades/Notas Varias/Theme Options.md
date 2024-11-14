```
## Basic
- [ ] to-do
- [/] incomplete
- [x] done
- [-] canceled
- [>] forwarded
- [<] scheduling

## Extras
- [?] question
- [!] important
- [*] star
- ["] quote
- [l] location
- [b] bookmark
- [i] information
- [S] savings
- [I] idea
- [p] pros
- [c] cons
- [f] fire
- [k] key
- [w] win
- [u] up
- [d] down
- [D] draft pull request
- [P] open pull request
- [M] merged pull request
```


- *Cursiva*: `*texto en cursiva*` o `_texto en cursiva_` → *texto en cursiva*
- **Negrita**: `**texto en negrita**` o `__texto en negrita__` → **texto en negrita**
- ***Negrita y cursiva***: `***texto en negrita y cursiva***` o `___texto en negrita y cursiva___` → ***texto en negrita y cursiva***
- ~~Tachado~~: `~~texto tachado~~` → ~~texto tachado~~
- `Código en línea`: `` `texto en código` `` → `texto en código`
- # Encabezado 1
## Encabezado 2
### Encabezado 3

- Bloque de código:
  ```markdown
```

[artisticat1/obsidian-tikzjax: Render LaTeX and TikZ diagrams in your notes (github.com)](https://github.com/artisticat1/obsidian-tikzjax)

$$ I_{D}= I_{S}(e^{\frac{V_{D}}{nV_{T}}}-1)$$



```tikz
\usepackage{circuitikz}
\begin{document}

\begin{circuitikz}[american, voltage shift=0.5]
\draw (0,0)
to[isource, l=$I_0$, v=$V_0$] (0,3)
to[short, -*, i=$I_0$] (2,3)
to[R=$R_1$, i>_=$i_1$] (2,0) -- (0,0);
\draw (2,3) -- (4,3)
to[R=$R_2$, i>_=$i_2$]
(4,0) to[short, -*] (2,0);
\end{circuitikz}

\end{document}
```
[HoLaTeX](https://holatex.app/)


$$\LARGE I_{D}= I_{S}(e^{\frac{V_{D}}{nV_{T}}}-1)$$
Alt+96 = "``"
Alt + 94 = "^"
Alt + 92 =  "\"
