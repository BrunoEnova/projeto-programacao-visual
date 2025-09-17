# Pseudo-elemento

🎯 O que é um pseudo-elemento?

Um pseudo-elemento é uma palavra-chave no CSS que permite estilizar partes específicas de um elemento HTML, sem precisar alterar o HTML diretamente.

Ele é usado com dois-pontos duplos ::, seguido do nome do pseudo-elemento.

```css
seletor::pseudo-elemento {
  propriedade: valor;
}
```

Exemplo:

```css
p::first-letter {
  font-size: 200%;
  color: red;
}
```

👉 Isso aumenta a primeira letra de todos os parágrafos.

🔸 Pseudo-elementos mais comuns
| Pseudo-elemento | O que faz |
|-----------------|---------------------------------------------------------------------------|
| `::before` | Insere conteúdo antes do conteúdo real do elemento. |
| `::after` | Insere conteúdo depois do conteúdo real. |
| `::first-letter`| Estiliza a primeira letra de um texto. |
| `::first-line` | Estiliza a primeira linha de um texto. |
| `::selection` | Estiliza o texto que o usuário seleciona com o mouse. |
| `::marker` | Estiliza os marcadores de listas (`ul`, `ol`). |

Exemplo prático 1

- html

  ```html
  <article>
    <h1>Já imaginou?</h1>

    <p class="coluna1">
      Já imaginou quanto tempo você economizaria se o redeploy não fosse
      necessário ao adicionar um novo método em uma classe ou ao alterar um XML
      ou anotação do seu framework preferido?
    </p>

    <p class="coluna2">
      Em Maio de 2015, no evento Voxxed Days Istanbul, conversei com Reza
      Rahman, que é evangelista Java EE na Oracle Corporation.
    </p>
  </article>

  <footer>Todos os direitos reservados.</footer>
  ```

- css

  ```css
  body {
    font-size: 32px;
  }

  h1 {
    margin: 0;
  }

  article {
    background-color: #0f0;
  }

  footer {
    background-color: yellow;
    text-align: center;
  }

  .coluna1,
  .coluna2 {
    background-color: #ccc;
  }

  .coluna1 {
    float: left;
    width: 48%;
  }

  .coluna2 {
    float: right;
    width: 48%;
  }

  /*REMOVER PROPRIEDADE*/
  article > p::first-letter {
    font-size: 60px;
    color: red;
  }

  /*REMOVER PROPRIEDADE*/
  h1::before {
    content: "Título: ";
  }

  /*REMOVER PROPRIEDADE*/
  h1::after {
    content: " - Artigo";
  }

  /*REMOVER PROPRIEDADE*/
  article::after {
    content: "";
    display: block;
    clear: both;
  }
  ```
