# Meta tag viewport

📌 O que é a Meta Tag viewport?

A meta tag viewport é usada no HTML para controlar como uma página é exibida em dispositivos móveis.

Ela define o tamanho da viewport (a área visível do site no navegador) e a escala inicial da renderização, permitindo que o site se adapte corretamente a telas menores — como celulares e tablets.

📖 Viewport = área visível da página no navegador (sem rolagem).

Exemplo

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link rel="stylesheet" href="css/estilos.css" />
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

    <script>
      document.write(
        "<h1>" + window.innerWidth + "x" + window.innerHeight + "</h1>"
      );
    </script>
  </body>
</html>
```

```css
body {
  margin: 0;
}

h1 {
  margin: 0;
}

.caixa {
  width: 300px;
  height: 300px;
  background-color: red;
}
```

[Site não responsivo](https://arngren.net/)
[Site responsivo](https://www.nike.com/)
