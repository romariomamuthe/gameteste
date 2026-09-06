# Sprites do personagem principal

Pacote com 19 posturas separadas em PNG de 256 × 256 px. Todos os arquivos usam o mesmo ponto de apoio (`anchor`) em **x: 128, y: 246**, facilitando a troca de quadros sem fazer o personagem pular de posição.

## Estrutura sugerida no GitHub

```text
assets/
  player/
    idle_01.png
    walk_01.png
    walk_02.png
    ...
    sprites.json
```

## Carregamento no HTML

```js
const BASE_URL = 'https://raw.githubusercontent.com/USUARIO/REPOSITORIO/main/assets/player/';

async function carregarSprites() {
  const manifest = await fetch(BASE_URL + 'sprites.json').then(r => r.json());
  const imagens = {};

  await Promise.all(Object.entries(manifest.frames).map(([nome, frame]) =>
    new Promise((resolve, reject) => {
      const img = new Image();
      img.onload = () => { imagens[nome] = img; resolve(); };
      img.onerror = reject;
      img.src = BASE_URL + frame.file;
    })
  ));

  return { manifest, imagens };
}
```

Para desenhar uma pose no Canvas:

```js
ctx.drawImage(imagens.walk_01, player.x - 128, player.y - 246, 256, 256);
```

Use `walk_01`, `walk_02` e `walk_03` em sequência para a caminhada. O arquivo `special_grab_01.png` contém dois personagens porque a pose original já apresenta o golpe com o oponente.
