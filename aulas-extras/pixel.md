# 🧱 O que é o px no CSS?

No CSS, px (pixel) é uma unidade de medida absoluta, usada para definir tamanhos de elementos, espaçamentos, fontes, bordas, margens, etc.

## 📌 Definição técnica:

1px no CSS representa um único "pixel lógico" na tela, e não necessariamente um pixel físico, especialmente em dispositivos com alta densidade (como telas Retina).

Exemplo

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="utf-8" />

    <link rel="stylesheet" href="css/pixel.css" />
  </head>
  <body>
    <div class="caixa">
      <h1>Economizar tempo com redeploy</h1>

      <p>
        Já imaginou quanto tempo você economizaria se o redeploy não fosse
        necessário ao adicionar um novo método em uma classe ou ao alterar um
        XML ou anotação do seu framework preferido?
      </p>
    </div>
  </body>
</html>
>
```

```css
.caixa {
  width: 600px;
  padding: 20px;
  font-size: 12px;

  background-color: #ccc;
  border: 5px solid black;
}
```
