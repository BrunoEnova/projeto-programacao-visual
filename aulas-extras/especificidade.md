# 🎨 Especificidade em CSS

## 🧩 O que é especificidade?

**Especificidade** é um sistema de pontuação que o CSS usa para decidir **qual regra será aplicada** quando há conflito entre seletores.

Quando duas ou mais regras definem a mesma propriedade (`color`, `background`, etc.) para um elemento, o navegador usa a **especificidade** para escolher qual delas vence.

---

## ⚖️ Hierarquia básica

Quando várias regras se aplicam ao mesmo elemento, a ordem de prioridade é:

1. **Estilos inline** (atributo `style=""` no HTML)
2. **IDs** (`#id`)
3. **Classes, pseudo-classes e atributos** (`.classe`, `:hover`, `[type="text"]`)
4. **Elementos e pseudo-elementos** (`div`, `p`, `::before`)
5. **Empate →** o **último declarado** no CSS vence

---

## 🔢 Como calcular a especificidade

Podemos pensar na especificidade como uma pontuação representada por quatro números:  
`(a, b, c, d)`

| Tipo de seletor                   | Exemplo                            | Valor        |
| --------------------------------- | ---------------------------------- | ------------ |
| Inline                            | `<div style="color:red">`          | (1, 0, 0, 0) |
| ID                                | `#menu`                            | (0, 1, 0, 0) |
| Classe, atributo ou pseudo-classe | `.item`, `[type="text"]`, `:hover` | (0, 0, 1, 0) |
| Elemento ou pseudo-elemento       | `div`, `p`, `::before`             | (0, 0, 0, 1) |

O navegador compara da esquerda para a direita (como se fosse um número decimal).

---

## 💡 Exemplos práticos

```css
/* 1) Seletor de elemento */
p {
  color: blue; /* especificidade (0,0,0,1) */
}

/* 2) Seletor de classe */
.texto {
  color: red; /* especificidade (0,0,1,0) */
}

/* 3) Seletor de ID */
#principal {
  color: green; /* especificidade (0,1,0,0) */
}
```

```html
<p id="principal" class="texto">Olá, mundo!</p>
```

⚠️ Dicas importantes

🚫 Evite usar !important, pois ele força uma regra a vencer todas as outras, o que dificulta a manutenção do código.

🧠 Prefira aumentar a especificidade naturalmente, combinando seletores quando necessário:

section .texto { color: red; }

🕒 Ordem importa: se dois seletores tiverem a mesma especificidade, o último no arquivo CSS é aplicado.

✨ Resumo rápido:

Inline > ID > Classe > Elemento

- Exmeplo 1

```css
body {
  font-size: 32px;
}

/*
h1 {
  color: red;
}
*/

#logo {
  /* 100 */
  color: green;
}

.amarelo {
  /* 010 */
  color: yellow;
}

h1 {
  /* 001 */
  color: blue !important;
}
```

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="utf-8" />

    <link rel="stylesheet" href="css/exemplo1.css" />
  </head>
  <body>
    <h1 id="logo" class="amarelo">AlgaWorks</h1>
  </body>
</html>
```

Exemplo 2

```css
body {
  font-size: 32px;
}

/*
h1 {
  color: red;
}
*/

body {
  font-size: 32px;
}

header#cabecalho h1.logo {
  /* 112 */
  color: yellow;
}

header#cabecalho .logo {
  /* 111 */
  color: purple;
}

#cabecalho .logo {
  /* 110 */
  color: red;
}

header .logo {
  /* 011 */
  color: green;
}

.logo {
  color: blue; /* 010 */
}
```

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="utf-8" />

    <link rel="stylesheet" href="css/exemplo2.css" />
  </head>
  <body>
    <header id="cabecalho">
      <h1 class="logo" style="color: orange">AlgaWorks</h1>
    </header>
  </body>
</html>
```
