# unit3d-css-custom

Temas CSS de usuário para trackers [UNIT3D](https://github.com/HDInnovations/UNIT3D-Community-Edition).

## Locadora (retrô)

`locadora-retro.css`: visual moderno com nostalgia de locadora de vídeo. Prateleiras azul-marinho, letreiro de néon, etiquetas de fita VHS, display de videocassete e um leve chiado de tubo CRT. O pôster da página do torrent vira um estojo VHS gasto, com faixa "LOCADORA HOME VIDEO" e bolinha de preço "72H".

Ele é aplicado por cima do tema escuro escolhido no perfil e mantém o layout próprio do tracker: header em duas linhas, conteúdo com até 1640px.

### Como usar

Em **Configurações → Geral → CSS customizado** (campo `custom_css`), cole uma das URLs abaixo e salve. Depois, recarregue a página com Ctrl+F5.

| Canal | URL |
|---|---|
| Estável (tag) | `https://cdn.jsdelivr.net/gh/USUARIO/unit3d-css-custom@v1/locadora-retro.css` |
| Último estável (`main`) | `https://cdn.jsdelivr.net/gh/USUARIO/unit3d-css-custom@main/locadora-retro.css` |
| Em teste (`dev`) | `https://cdn.jsdelivr.net/gh/USUARIO/unit3d-css-custom@dev/locadora-retro.css` |

Troque `USUARIO` pelo dono do repositório. Para a versão minificada, use `.min.css` no fim da URL.

### Fluxo de versões

- **`dev`:** iteração e testes.
- **`main`:** estável.
- **Tags `vN`:** o que é divulgado aos usuários.

URLs de branch ficam em cache no jsDelivr por algumas horas. Para forçar a atualização depois de um push, abra a mesma URL trocando `cdn.jsdelivr.net` por `purge.jsdelivr.net`. URLs de tag ou de commit não têm esse problema.

**Não use** o link "Raw" do GitHub ou do Gist. Ele é servido como `text/plain` com `nosniff`, e o navegador se recusa a aplicar o arquivo como CSS.

### Notas para quem for editar

- O tema base do UNIT3D define `html { font-size: 10px }`, ou seja, 1rem = 10px. Na camada Locadora, use **px**.
- O bloco "Layout (herdado)" vem do CSS anterior do tracker e usa `rem` calibrado nessa escala.
- As cores dos adesivos do Random Media dependem dos IDs de categoria do tracker (`/similar/{id}.`): Séries = 2, Animes = 6.
- O texto da bolinha do pôster fica na variável `--lc-poster-sticker`.
