# Memory Game

Este repositório contém o código de um jogo da memória simples e interativo desenvolvido com HTML, CSS e JavaScript. O objetivo do jogo é encontrar os pares de cartas que possuem o mesmo emoji.

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

```
Memory_Game/
├── index.html            # Estrutura do jogo (HTML)
├── src/
│   ├── styles/
│   │   ├── reset.css    # Reset de estilos padrão
│   │   ├── main.css     # Estilos principais do jogo
│   ├── scripts/
│       ├── engine.js    # Lógica do jogo (JavaScript)
```

### Descrição dos Arquivos

- **index.html**: Contém a estrutura básica da página, incluindo um container para o jogo e um botão de "Reset Game".
- **reset.css**: Remove estilos padrão dos navegadores para garantir consistência.
- **main.css**: Define o estilo visual do jogo, como cores, layout e animações.
- **engine.js**: Gerencia a lógica do jogo, incluindo o embaralhamento de emojis, verificação de pares e reinício do jogo.

## Como Jogar
1. Abra o arquivo `index.html` no navegador.
2. Clique em uma carta para revelá-la.
3. Encontre a carta correspondente (com o mesmo emoji).
4. Continue até encontrar todos os pares.
5. Ao finalizar, o jogo exibe uma mensagem de vitória.

## Alteração no Código

Foi realizada a seguinte alteração no código JavaScript para corrigir um comportamento indesejado:

### Antes:
```javascript
function handleClick() {
    if (openCards.length < 2) {
        this.classList.add("boxOpen");
        openCards.push(this);
    }

    if (openCards.length == 2) {
        setTimeout(checkMatch, 500);
    }
}
```

### Depois:
```javascript
function handleClick() {
    if (!this.classList.contains("boxOpen") && openCards.length < 2) {
        this.classList.add("boxOpen");
        openCards.push(this);
    }

    if (openCards.length == 2) {
        setTimeout(checkMatch, 500);
    }
}
```

### Motivo da Alteração
A mudança foi feita para evitar que o jogador pudesse clicar repetidamente na mesma carta e adicioná-la ao array `openCards` mais de uma vez. Isso corrigiu o comportamento em que uma única carta poderia ser tratada como um par, comprometendo a lógica do jogo.

## Tecnologias Utilizadas
- **HTML5**: Para a estrutura do jogo.
- **CSS3**: Para estilização e layout responsivo.
- **JavaScript**: Para a lógica do jogo e manipulação da DOM.

## Como Executar o Projeto
1. Clone este repositório:
   ```bash
   git clone https://github.com/tayanne1/Memory_Game.git
   ```
2. Navegue até a pasta do projeto:
   ```bash
   cd Memory_Game
   ```
3. Abra o arquivo `index.html` no navegador de sua preferência.

