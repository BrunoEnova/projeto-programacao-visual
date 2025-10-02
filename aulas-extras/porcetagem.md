# 📌 O que é % no CSS?

A unidade % (porcentagem) em CSS é uma unidade de medida relativa. Ela não tem valor fixo, pois depende do elemento pai (ou do contexto específico onde está sendo aplicada).

1% representa 1 parte de 100 do valor de referência (pai/contexto).

## 📐 Comportamento da Porcentagem no CSS

A forma como a porcentagem se comporta depende da propriedade CSS onde está sendo usada:

| **Propriedade CSS**              | **Referência da %**                               |
| -------------------------------- | ------------------------------------------------- |
| `width`                          | Largura do elemento pai                           |
| `height`                         | Altura do elemento pai _(se definida)_            |
| `padding`                        | Largura do elemento pai                           |
| `margin`                         | Largura do elemento pai                           |
| `font-size`                      | Tamanho da fonte do elemento pai                  |
| `top`, `left`, `right`, `bottom` | Tamanho do elemento pai (posicionamento relativo) |

Exemplo

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="utf-8" />

    <link rel="stylesheet" href="css/percentual.css" />
  </head>
  <body>
    <div class="container">
      <div class="caixa">
        <h1>Economizar tempo com redeploy</h1>

        <p>
          Já imaginou quanto tempo você economizaria se o redeploy não fosse
          necessário ao adicionar um novo método em uma classe ou ao alterar um
          XML ou anotação do seu framework preferido?
        </p>
      </div>
    </div>
  </body>
</html>
```

```css
* {
  box-sizing: border-box;
}

html {
  font-size: 62.5%; /* 10px = 10 / 16 * 100 = 62.5% (em relação à fonte do navegador) */
}

.container {
  width: 1000px;
  background-color: yellow;
}

.caixa {
  width: 50%;
  padding: 10%;
  margin-top: 10%;

  font-size: 200%; /* 20px */

  background-color: #ccc;
  border: 5px solid black;
}

h1 {
  font-size: 250%; /* 50px */
}

p {
  font-size: 150%; /* 30px */
}
```
