# Modus Marp Themes

Temas [Marp](https://marp.app/) baseados nos [Modus Themes](https://protesilaos.com/emacs/modus-themes) do Protesilaos Stavrou. Conformes com **WCAG AAA** (contraste ≥7:1) e com variantes para **daltonismo**.

## Instalação (VS Code + Marp for VS Code)

Abra as *settings* (`Cmd+,` ou `Ctrl+,`), clique em **Edit in settings.json** e adicione:

```json
"markdown.marp.themes": [
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-operandi.css",
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-vivendi.css",
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-operandi-tinted.css",
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-vivendi-tinted.css",
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-operandi-deuteranopia.css",
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-vivendi-deuteranopia.css",
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-operandi-tritanopia.css",
  "https://raw.githubusercontent.com/viniciusdias2902/modus-marp-themes/refs/heads/main/modus-vivendi-tritanopia.css"
]
```

Recarregue o VS Code (`Cmd+Shift+P` → *Reload Window*).

> Para Marp CLI, passe cada arquivo com `--theme path/to/arquivo.css`.

## Uso

No frontmatter do seu `.md`, escolha um dos temas:

```markdown
---
marp: true
theme: modus-operandi
paginate: true
---
```

## Temas disponíveis

| Nome | Tipo | Quando usar |
|------|------|-------------|
| `modus-operandi` | Light, neutro | Padrão claro |
| `modus-vivendi` | Dark, neutro | Padrão escuro |
| `modus-operandi-tinted` | Light, sépia | Leitura prolongada |
| `modus-vivendi-tinted` | Dark, azulado | Ambientes de baixa luz |
| `modus-operandi-deuteranopia` | Light, sem vermelho/verde | Daltonismo red-green |
| `modus-vivendi-deuteranopia` | Dark, sem vermelho/verde | Daltonismo red-green |
| `modus-operandi-tritanopia` | Light, sem azul/amarelo | Daltonismo blue-yellow |
| `modus-vivendi-tritanopia` | Dark, sem azul/amarelo | Daltonismo blue-yellow |

## Funcionalidades

### Classes de slide

Aplique com `<!-- _class: nome -->` no topo do slide.

- **`lead`** — slide de título centralizado com gradiente e brasão da UESPI embutido.
- **`compact`** — reduz fonte para 22px e código para 0.78em. Útil para slides com código longo que estouram a página. *Disponível apenas em `modus-operandi` e `modus-vivendi`.*

### Elementos utilitários

Use com `<div class="nome">...</div>`.

- **`highlight`** — caixa de destaque (amarelo em light, ajustado por variante).
- **`info`** — caixa informativa (ciano).
- **`success`** / **`error`** — caixas de status. *Disponíveis apenas nas variantes para daltonismo*, com cores seguras para a deficiência correspondente.

### Tipografia

- Fonte principal: `Inter`, com fallback para `Noto Sans`, `Helvetica Neue`, `Arial`.
- Fonte de código: `JetBrains Mono`, com fallback para `Fira Code`, `Source Code Pro`.
- Hierarquia: `h1` com borda colorida, `h2` em cor de destaque, `h3` em ciano.

### Syntax highlighting

Suporte a classes do `highlight.js` (keyword, string, comment, function, type, tag, etc.) com paleta coerente com cada variante.

### Elementos suportados

Tabelas, listas, blockquotes, imagens, `<code>` inline e blocos `<pre>` — todos estilizados.

## Exemplo

Veja [`exemplo-react.md`](./exemplo-react.md) para um deck completo demonstrando todos os recursos.

## Acessibilidade

Todos os temas atingem contraste **WCAG AAA**. Variantes para daltonismo substituem o eixo de cor problemático:

- **Deuteranopia/Protanopia** (red-green): paleta baseada em azul/amarelo. Diffs usam blue/yellow em vez de green/red.
- **Tritanopia** (blue-yellow): paleta baseada em vermelho/ciano. Diffs usam red/cyan.

## Créditos

- Paleta original: [Modus Themes](https://protesilaos.com/emacs/modus-themes) por Protesilaos Stavrou.
- Adaptação para Marp: Vinícius Dias.
