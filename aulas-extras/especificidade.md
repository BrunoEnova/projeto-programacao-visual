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

### Atividade

Perfeito! 🎯
Aqui vai uma atividade completa sobre especificidade em CSS, pronta para ser usada em aula, trabalhos ou estudos individuais — com enunciado, instruções, código base e perguntas.

# 🧠 Atividade: Entendendo a Especificidade em CSS

## 🎯 Objetivo

Compreender como o navegador decide **qual regra CSS tem prioridade** quando múltiplas regras afetam o mesmo elemento.

---

## 🧩 Instruções

1. Analise o código HTML e CSS abaixo.
2. **Preveja** qual será o estilo final de cada elemento.
3. **Explique** por que essa regra foi aplicada, com base na especificidade.
4. Faça modificações sugeridas para testar o comportamento do CSS.

---

## 💻 Código base

### HTML

```html
<!DOCTYPE html>
<html lang="pt-br">
  <head>
    <meta charset="UTF-8" />
    <title>Especificidade CSS</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h1 id="titulo" class="destaque">Bem-vindo!</h1>
    <p class="texto">Este é um parágrafo de exemplo.</p>
    <p id="mensagem" class="texto especial">Mensagem importante!</p>
    <button class="botao">Clique aqui</button>
  </body>
</html>

CSS /* Regra 1 */ p { color: blue; } /* Regra 2 */ .texto { color: red; } /*
Regra 3 */ #mensagem { color: green; } /* Regra 4 */ p.especial { color: purple;
} /* Regra 5 */ #mensagem.texto { color: orange; } /* Regra 6 */ button {
background: gray; } /* Regra 7 */ .botao { background: yellow; } /* Regra 8
(inline simulada) */ /* Imagine que no HTML o botão tivesse: style="background:
pink;" */ 🧮 Parte 1 – Cálculo de especificidade Complete a tabela a seguir:
Regra Seletor Especificidade Cor/Estilo aplicado 1 p 2 .texto 3 #mensagem 4
p.especial 5 #mensagem.texto 6 button 7 .botao 8 style="" (inline) 🧠 Parte 2 –
Questões Qual será a cor final do parágrafo com o texto “Mensagem importante!”?
Por que a regra #mensagem.texto tem prioridade sobre .texto? Se adicionarmos
!important em .texto, qual regra vencerá? O que aconteceria se trocássemos a
ordem das regras #mensagem e #mensagem.texto no CSS? No botão, qual cor de fundo
será exibida se adicionarmos style="background: pink;" no HTML? 🧩 Parte 3 –
Desafio extra Ajuste o código para que: Todos os parágrafos tenham cor azul,
exceto o que tem id="mensagem", que deve ficar roxo. O botão tenha fundo verde,
mas mude para vermelho quando o mouse passar por cima (:hover). Use seletores
com a menor especificidade possível! 🏁 Conclusão Após completar a atividade,
você deve ser capaz de: ✅ Explicar como o CSS calcula a especificidade. ✅
Prever qual regra será aplicada em conflitos de estilo. ✅ Utilizar seletores de
forma inteligente para evitar !important.
```
