📌 O que é Layout Fixo?
🧱 Layout fixo (Fixed layout)

É um tipo de layout onde as larguras dos elementos são definidas em unidades fixas, geralmente em pixels (px). Isso significa que o conteúdo não se adapta automaticamente ao tamanho da tela.

🔹 Características do Layout Fixo:
Característica Descrição
🧱 Unidade usada px (pixels)
📐 Largura Fixa, ex: width: 960px
📱 Responsivo? ❌ Não, a menos que use media queries
✅ Vantagens Controle total sobre o design
❌ Desvantagens Pode quebrar em telas pequenas; exige rolagem horizontal
🧑‍💻 Exemplo de Layout Fixo:
.container {
width: 960px;
margin: 0 auto;
}

Esse container sempre terá 960px, independentemente do tamanho da tela.

🌊 O que é Layout Fluido?
🌀 Layout fluido (Fluid layout ou Liquid layout)

É um layout onde as larguras são definidas em unidades relativas, como porcentagem (%), fazendo com que os elementos se adaptem ao tamanho da tela automaticamente.

🔹 Características do Layout Fluido:
Característica Descrição
💧 Unidade usada %, vw (viewport width)
📐 Largura Relativa, ex: width: 80%
📱 Responsivo? ✅ Parcialmente (mais adaptável)
✅ Vantagens Adapta-se bem a vários tamanhos de tela
❌ Desvantagens Pode distorcer o layout em telas muito grandes ou muito pequenas
🧑‍💻 Exemplo de Layout Fluido:
.container {
width: 80%;
margin: 0 auto;
}

A largura do container será 80% da tela ou do elemento pai — ou seja, fluida.
