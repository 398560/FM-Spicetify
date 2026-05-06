# FM-Modulos(Spicetify)

Modulos CSS reutilizaveis para montar temas Spicetify com identidade FM.

## Modulos

- `fm-cover-wallpaper.spicetify.css`: cria um wallpaper gigante baseado em capa/imagem.
- `fm-clean-reset.spicetify.css`: remove fundos opacos e gradientes padrao do Spotify.
- `fm-clean-layout.css`: ajusta espacamento, proporcoes, radius e remove ruidos visuais.
- `fm-aero-glass.spicetify.css`: vidro fosco estilo Aero Glass. Arquivo preservado como enviado.
- `fm-depth.css`: adiciona sombras, elevacao e foco com profundidade.
- `fm-soft-controls.spicetify.css`: botoes, progress bar, cards, scrollbars e detalhes com accent.
- `fm-accent-glow.css`: glow e tint baseados em `--spice-button`.
- `fm-typography.css`: fontes, pesos e hierarquia tipografica.
- `fm-watermark.css`: marca d'agua FM discreta.
- `fm-interface-fixes.spicetify.css`: corrige hitboxes, z-index, right sidebar, cover expandido, cinema e flickers pretos.

## Ordem sugerida

Use o modulo de fixes por ultimo, porque ele precisa vencer seletores dos outros modulos.

```css
@import url("./modules/fm-cover-wallpaper.spicetify.css");
@import url("./modules/fm-clean-reset.spicetify.css");
@import url("./modules/fm-clean-layout.css");
@import url("./modules/fm-aero-glass.spicetify.css");
@import url("./modules/fm-depth.css");
@import url("./modules/fm-soft-controls.spicetify.css");
@import url("./modules/fm-accent-glow.css");
@import url("./modules/fm-typography.css");
@import url("./modules/fm-watermark.css");
@import url("./modules/fm-interface-fixes.spicetify.css");
```

## Variaveis principais

```css
:root {
  --fm-wallpaper-image: url("./images/minha-imagem.png");
  --fm-accent-rgb: 125, 147, 135;
  --fm-radius: 8px;
  --fm-expanded-cover-size: clamp(220px, 38vmin, 420px);
}
```

O modulo de wallpaper tambem tenta usar `--fm-cover-url` ou `--image_url` quando algum tema/script dinamico ja define a capa atual.

## Validacao

Todos os modulos CSS foram checados quanto a chaves, parenteses, colchetes e aspas desbalanceadas.

O arquivo `fm-aero-glass.spicetify.css` foi mantido sem alteracoes.

Nos novos modulos importados do Claude, foram feitos dois ajustes de compatibilidade:

- `fm-watermark.css`: usa `.Root::after` para nao sobrescrever o overlay do wallpaper em `.Root__top-container::after`.
- `fm-clean-layout.css`: aceita tanto a classe original quanto a variante usada no Hazy local para o overlay de artista.
