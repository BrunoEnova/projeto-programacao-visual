# Flutuar

Conceito de flutuar (ou float) em CSS foi uma técnica popular usada por muito tempo para criar layouts e alinhar elementos na página. Embora técnicas mais modernas, como Flexbox e CSS Grid, tenham substituído o uso de float para a maioria dos casos, ainda é importante entender como ele funciona.

O que é float em CSS?

A propriedade float em CSS permite que você faça um elemento "flutuar" para a esquerda ou para a direita dentro de seu contêiner. Quando você flutua um elemento, ele se move para a direção especificada (esquerda ou direita), e o restante do conteúdo ao redor tenta preencher o espaço que sobra.

```css
elemento {
  float: left; /* Ou 'right' */
}
```

- float: left: Faz o elemento flutuar para a esquerda.

- float: right: Faz o elemento flutuar para a direita.

Exemplos 1

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

  <footer class="clearfix">Todos os direitos reservados.</footer>
  ```

- css

  ```css
  body {
    font-size: 26px;
  }

  img {
    /*REMOVER PROPRIEDAS*/
    float: right;
    margin-right: 20px;
  }
  ```

  Exemplo 2

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

    <!-- <div class="clearfix" ></div> -->
  </article>

  <!-- REMOVER ELEMENTO -->
  <footer class="clearfix">Todos os direitos reservados.</footer>
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

  /*Seletor agregado*/
  .coluna1,
  .coluna2 {
    background-color: #ccc;
  }

  /*REMOVER PROPRIEDADE*/
  .coluna1 {
    float: left;
    width: 48%;
  }
  /*REMOVER PROPRIEDADE*/
  .coluna2 {
    float: right;
    width: 48%;
  }

  /*REMOVER PROPRIEDADE*/
  .clearfix {
    clear: both;
  }
  ```
