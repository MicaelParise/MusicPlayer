# 🎧 Music Player

Um player de música web, simples e sem servidor: abra o `index.html` no
navegador e já está tocando. Tema escuro, com destaque em indigo, layout
responsivo para notebook, tablet e celular, e uma estrutura pensada para
tornar trivial adicionar novas músicas (com ou sem capa).

## Tecnologias

Tudo via CDN, sem instalação, sem build e sem dependências de Node:

- **HTML + JavaScript puro** — a lógica do player é um componente [Alpine.js](https://alpinejs.dev/).
- **[Tailwind CSS](https://tailwindcss.com/)** (via CDN) para o layout e o visual.
- **[Alpine.js](https://alpinejs.dev/)** (via CDN) para reatividade (play/pause, progresso, lista, etc.).
- **Material Icons** (via Google Fonts) para os ícones dos controles.

## Como rodar

Não precisa de servidor, build ou instalação de pacotes. Basta abrir o
arquivo `index.html` diretamente no navegador (duplo clique ou
"Abrir com..." o navegador de sua preferência).

## Funcionalidades

- Tocar/pausar, avançar/voltar faixa, e pular direto para um ponto da música clicando na barra de progresso.
- Repetir playlist, repetir uma única música ou tocar em ordem aleatória (ícone de repetição).
- Lista de músicas com duração de cada faixa, sempre visível em telas grandes (como uma barra lateral) e em painel deslizante em telas pequenas.
- Capa de cada música carregada automaticamente ao tocar; quando a música não tem capa (ou o arquivo de imagem falha ao carregar), uma capa padrão é exibida no lugar.
- Layout responsivo: ocupa a tela inteira, sem rolagem desnecessária — a única parte que rola é a lista de músicas, quando ela não cabe inteira na tela.

## Estrutura de pastas

```
MusicPlayer/
├── index.html              # página única do player
├── assets/
│   ├── css/
│   │   └── style.css       # pequenos ajustes que o Tailwind não cobre (fonte, scrollbar)
│   ├── js/
│   │   ├── songs.js         # dados das músicas (nome, artista, capa, arquivo de audio)
│   │   └── player.js        # componente Alpine.js com toda a logica do player
│   ├── icons/               # favicons e manifest do site
│   ├── images/               # capas das músicas (.jpg)
│   └── music/                 # arquivos de áudio (.mp3)
├── LICENSE
└── README.md
```

## Como adicionar novas músicas

Toda música é um objeto dentro do array `allMusic`, em
[`assets/js/songs.js`](assets/js/songs.js).

### Música com capa

1. Coloque o arquivo de áudio em `assets/music/`, por exemplo `assets/music/minha-musica.mp3`.
2. Coloque a capa em `assets/images/`, por exemplo `assets/images/minha-musica.jpg`.
3. Adicione um objeto na lista:

```js
{
  name: "Nome da música",
  artist: "Nome do artista",
  img: "minha-musica", // sem extensão — o player sempre usa .jpg
  src: "minha-musica"  // sem extensão — o player sempre usa .mp3
}
```

### Música sem capa

Basta omitir o campo `img`. O player usa automaticamente a capa padrão
(`assets/images/disc.jpg`) — inclusive se você informar um `img` cujo
arquivo não existe, ou que falhe ao carregar.

```js
{
  name: "Nome da música",
  artist: "Nome do artista",
  src: "minha-musica"
}
```

> `name`, `artist` e `src` são obrigatórios. `img` é sempre opcional.

## Créditos

- Ícones do player: [Material Icons](https://fonts.google.com/icons) (Google).
- Favicon: gerado a partir de um gráfico do [Twemoji](https://github.com/twitter/twemoji) (CC-BY 4.0) — veja [`assets/icons/about.txt`](assets/icons/about.txt).

## Licença

Distribuído sob a licença MIT — veja [LICENSE](LICENSE).
