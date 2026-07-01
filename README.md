# 🎧 Music Player

Player de música web com tema escuro, feito com HTML, Tailwind CSS e
Alpine.js (tudo via CDN, sem build).

🔗 Acesse pelo GitHub Pages: **https://micaelparise.github.io/MusicPlayer/**

## Como adicionar novas músicas

Toda música é um objeto dentro do array `allMusic`, em
[`assets/js/songs.js`](assets/js/songs.js).

**Com capa** — coloque o áudio em `assets/music/` e a capa (`.jpg`) em `assets/images/`, depois adicione:

```js
{
  name: "Nome da música",
  artist: "Nome do artista",
  img: "minha-musica", // sem extensão, deve existir em assets/images
  src: "minha-musica"  // sem extensão, deve existir em assets/music
}
```

**Sem capa** — basta omitir o campo `img`; o player usa a capa padrão automaticamente:

```js
{
  name: "Nome da música",
  artist: "Nome do artista",
  src: "minha-musica"
}
```

> `name`, `artist` e `src` são obrigatórios. `img` é opcional.

## Licença

Distribuído sob a licença MIT — veja [LICENSE](LICENSE).
