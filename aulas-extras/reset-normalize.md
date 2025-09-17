# Reset

Reset CSS é uma técnica que "reseta" ou remove quase todos os estilos padrão aplicados pelos navegadores aos elementos HTML. A ideia é começar com uma base completamente limpa, sem margens, paddings, fontes ou qualquer estilo herdado, para garantir que o visual seja mais consistente entre diferentes navegadores.

Características do Reset CSS:

Remove praticamente todos os estilos padrões.

Pode afetar a usabilidade, já que remove até estilos úteis (exemplo: listas, títulos).

Exemplo famoso: Eric Meyer Reset CSS

```css
/* Exemplo simples */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

Quando usar?

Quando você quer controle total e prefere construir todos os estilos do zero.

Em projetos onde a consistência visual entre navegadores é prioridade máxima.

# Normalize CSS

Normalize CSS é uma abordagem diferente que não remove todos os estilos, mas normaliza as diferenças entre navegadores. Ele mantém estilos úteis, corrige inconsistências e melhora a renderização dos elementos, garantindo uma base consistente sem apagar totalmente os estilos padrão.

Características do Normalize CSS:

Mantém estilos padrão úteis para acessibilidade e usabilidade.

Corrige bugs e inconsistências entre navegadores.

Menos agressivo que o reset, permitindo que o design seja construído em cima de uma base mais natural.

Popularmente usado em muitos frameworks modernos.

Você pode usar o arquivo oficial disponível em: [Normalize.css](https://github.com/necolas/normalize.css/) no GitHub.

| Aspecto     | Reset CSS                              | Normalize CSS                                     |
| ----------- | -------------------------------------- | ------------------------------------------------- |
| O que faz   | Remove todos os estilos padrão         | Ajusta e uniformiza estilos padrão                |
| Efeito      | Base “limpa” e neutra                  | Base consistente e natural                        |
| Usabilidade | Pode precisar estilizar tudo novamente | Mantém estilos úteis intactos                     |
| Uso comum   | Projetos que querem controle total     | Projetos que querem consistência e acessibilidade |
