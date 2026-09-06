# Sprites do Chefe Final

Pacote com 13 posturas individuais em PNG transparente de 320 × 320 px. Todos os quadros usam o ponto de apoio `x: 160, y: 312`.

## Estrutura sugerida

```text
character-boss-sprites/
  boss_idle_01.png
  boss_walk_01.png
  boss_walk_02.png
  boss_walk_03.png
  boss_walk_04.png
  boss_punch_01.png
  boss_kick_01.png
  boss_jump_punch_01.png
  boss_jump_kick_01.png
  boss_crouch_01.png
  boss_special_01.png
  boss_damage_01.png
  boss_knockdown_01.png
  sprites.json
```

## URL para o HTML

Depois de publicar a pasta, use uma base semelhante a:

```js
const BOSS_SPRITE_BASE =
  'https://raw.githubusercontent.com/USUARIO/REPOSITORIO/main/character-boss-sprites/';
```

O arquivo `sprites.json` informa os nomes, dimensões e ponto de ancoragem de cada quadro.
