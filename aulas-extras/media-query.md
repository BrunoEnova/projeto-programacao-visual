📌 O que são Media Queries?

Media Queries são recursos do CSS que permitem aplicar estilos diferentes dependendo do tipo de dispositivo ou das características da tela (como largura, altura, resolução, orientação, etc).

Elas são a base do design responsivo, permitindo adaptar o layout para celulares, tablets, notebooks e telas grandes.

🔧 Sintaxe básica
@media (condição) {
/_ estilos CSS aplicados somente se a condição for verdadeira _/
}

✅ Exemplo:
@media (max-width: 768px) {
body {
background-color: lightblue;
}
}

Neste caso, o fundo da página será azul apenas se a tela tiver até 768px de largura (ex: celular).

🎯 Como funcionam as Media Queries?

Media Queries usam expressões lógicas para verificar:

Tamanho da tela (width, height)

Tipo de mídia (screen, print, etc.)

Orientação (portrait, landscape)

Resolução (resolution, dpi)

Características específicas (hover, pointer, aspect-ratio...)

Se a condição for satisfeita, os estilos dentro do bloco serão aplicados.

| Expressão                | O que faz                                              |
| ------------------------ | ------------------------------------------------------ |
| `max-width`              | Aplica o estilo até um limite de largura               |
| `min-width`              | Aplica o estilo a partir de um limite de largura       |
| `max-height`             | Aplica o estilo até certa altura                       |
| `min-height`             | Aplica o estilo a partir de certa altura               |
| `orientation: portrait`  | Aplica se o dispositivo estiver na vertical            |
| `orientation: landscape` | Aplica se o dispositivo estiver na horizontal          |
| `hover: hover`           | Aplica se o dispositivo possui suporte a hover (mouse) |
