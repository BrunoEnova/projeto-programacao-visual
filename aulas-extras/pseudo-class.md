# Pseudo-class

🔹 O que é uma pseudo-classe em CSS?

Uma pseudo-classe é uma palavra-chave adicionada a seletores que especifica um estado especial de um elemento. Ela permite aplicar estilos a elementos com base em sua interação, posição ou estado atual, mesmo que esses estados não estejam diretamente presentes no HTML.

```css
a:hover {
  color: red;
}
```

| Pseudo-classe    | O que faz                                                          |
| ---------------- | ------------------------------------------------------------------ |
| `:hover`         | Estiliza o elemento quando o usuário passa o mouse sobre ele.      |
| `:active`        | Estiliza o elemento no momento em que está sendo clicado.          |
| `:focus`         | Estiliza o elemento que está em foco (ex: um input ativo).         |
| `:visited`       | Estiliza links que já foram visitados pelo usuário.                |
| `:first-child`   | Seleciona o primeiro filho de um elemento pai.                     |
| `:last-child`    | Seleciona o último filho de um elemento pai.                       |
| `:nth-child(n)`  | Seleciona o enésimo filho de um elemento pai (pode usar fórmulas). |
| `:not(selector)` | Seleciona todos os elementos que não correspondem ao seletor dado. |
| `:checked`       | Seleciona checkboxes ou radios que estão marcados.                 |
| `:disabled`      | Seleciona elementos de formulário desabilitados.                   |

Exemplo prático

```css
.botoa:focus,
.botao:hover {
  background-color: #0e6400;
}
```
