---
marp: true
theme: modus-operandi
paginate: true
---

<!-- _class: lead -->

# React

## Uma biblioteca para construir interfaces de usuário

---

# Sumário

1. O que é **React**?
2. Componentes e *JSX*
3. Hooks essenciais
4. Props vs. State
5. Boas práticas
6. Ecossistema

---

# O que é React?

**React** é uma biblioteca JavaScript declarativa, criada pelo *Facebook* em 2013, para a construção de interfaces de usuário baseadas em [componentes](https://react.dev/).

## Características principais

- **Declarativo** — descreva o *que* renderizar, não *como*
- **Baseado em componentes** — compõem UIs complexas a partir de blocos pequenos
- **Aprenda uma vez, escreva em qualquer lugar** — web, mobile, desktop

> Think of React components as JavaScript functions that accept arbitrary inputs and return elements describing what should appear on the screen.

---

# Componentes e JSX

Um componente é uma função que retorna **JSX** — uma extensão de sintaxe que mistura HTML com JavaScript.

```jsx
function Saudacao({ nome }) {
  return (
    <div className="card">
      <h1>Olá, {nome}!</h1>
      <p>Bem-vindo ao React.</p>
    </div>
  );
}

export default Saudacao;
```

Uso: `<Saudacao nome="Vinícius" />`

---

![bg right:40% w:80%](https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg)

# Hooks essenciais

Hooks permitem usar *estado* e outras funcionalidades do React em componentes funcionais.

- `useState` — gerencia estado local
- `useEffect` — lida com efeitos colaterais
- `useContext` — consome valores de contexto
- `useMemo` / `useCallback` — otimizações de performance
- `useRef` — referências mutáveis

---

<!-- _class: compact -->

# Exemplo: `useState` + `useEffect`

```jsx
import { useState, useEffect } from 'react';

function Contador() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Clicou ${count} vezes`;
  }, [count]);

  return (
    <button onClick={() => setCount(count + 1)}>
      Cliques: {count}
    </button>
  );
}
```

---

# Props vs. State

| Aspecto        | Props                       | State                        |
|----------------|-----------------------------|------------------------------|
| **Origem**     | Passadas pelo componente pai | Criado dentro do componente  |
| **Mutabilidade** | Imutáveis (read-only)     | Mutável via *setter*         |
| **Fluxo**      | Top-down                    | Local ao componente          |
| **Uso típico** | Configuração, dados         | Interação, UI dinâmica       |

---

# Boas práticas

<div class="highlight">

**Atenção!** Nunca modifique o *state* diretamente. Sempre use a função `setState` retornada pelo hook.

</div>

```jsx
// Errado
state.count = state.count + 1;

// Certo
setCount(prev => prev + 1);
```

- Prefira **componentes pequenos** e com responsabilidade única
- Extraia lógica para *custom hooks* quando for reutilizada
- Use `key` única em listas renderizadas

---

# Ecossistema

<div class="info">

**Dica:** O React sozinho resolve apenas a camada de visualização. Para aplicações completas, combine-o com outras bibliotecas.

</div>

| Categoria       | Opções comuns                      |
|-----------------|------------------------------------|
| Roteamento      | `react-router`, `tanstack-router`  |
| Estado global   | `zustand`, `redux-toolkit`, `jotai` |
| Data-fetching   | `tanstack-query`, `swr`            |
| Estilização     | `tailwindcss`, `styled-components` |
| Meta-framework  | `Next.js`, `Remix`, `Astro`        |

---

# Performance: memoização

```jsx
import { useMemo, memo } from 'react';

const ItemCaro = memo(function ItemCaro({ dado }) {
  const processado = useMemo(
    () => calcularCoisaCara(dado),
    [dado]
  );

  return <div>{processado}</div>;
});
```

> Use `memo` e `useMemo` com critério — otimizar antes de medir pode adicionar complexidade sem ganho real.

---

![bg left:35% w:70%](./uespi_brasao.svg)

# Considerações finais

React é uma ferramenta *poderosa*, mas o domínio vem com a prática.

1. Comece pequeno — um componente de cada vez
2. Leia a [documentação oficial](https://react.dev/)
3. Construa projetos reais
4. Estude o que cada hook faz antes de usá-lo

**Obrigado!**

---

<!-- _class: lead -->

# Perguntas?

## email@provedor.com
