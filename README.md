# unit3d-css-custom

Temas CSS de usuário para trackers [UNIT3D](https://github.com/HDInnovations/UNIT3D-Community-Edition).

## Locadora retrô

`locadora-retro.css`: visual moderno com o clima das locadoras de vídeo dos anos 80 e 90. Prateleiras azul-marinho, letreiro de néon, etiquetas de fita VHS, display de videocassete e um leve chiado de tubo CRT. O pôster da página do torrent vira um estojo VHS gasto, com uma faixa genérica "LOCADORA HOME VIDEO" e bolinha de preço "72H".

Ele é aplicado por cima do tema escuro escolhido no perfil e ajusta o layout: header em duas linhas, conteúdo com até 1640px.

### Como usar

Em **Configurações → Geral → CSS customizado** (campo `custom_css`), cole uma das URLs abaixo e salve. Depois, recarregue a página com Ctrl+F5.

| Canal | URL |
|---|---|
| Estável, recebe correções (recomendado) | `https://cdn.jsdelivr.net/gh/ohmadruga/unit3d-css-custom@1/locadora-retro.css` |
| Versão fixa | `https://cdn.jsdelivr.net/gh/ohmadruga/unit3d-css-custom@1.0.0/locadora-retro.css` |
| Último estável (`main`) | `https://cdn.jsdelivr.net/gh/ohmadruga/unit3d-css-custom@main/locadora-retro.css` |
| Em teste (`dev`) | `https://cdn.jsdelivr.net/gh/ohmadruga/unit3d-css-custom@dev/locadora-retro.css` |

A URL com `@1` sempre entrega a versão `1.x.x` mais recente e nunca pula para a `2.0.0`. Para a versão minificada, use `.min.css` no fim da URL.

**Não use** o link "Raw" do GitHub ou do Gist. Ele é servido como `text/plain` com `nosniff`, e o navegador se recusa a aplicar o arquivo como CSS.

### Versionamento

As versões seguem [SemVer](https://semver.org/lang/pt-BR/), com tags `vX.Y.Z` criadas sempre no `main`:

| Sobe | Quando | Exemplos |
|---|---|---|
| **MAJOR** (`v2.0.0`) | Quem usa vai estranhar ou precisar mexer em algo | Layout refeito, efeito marcante removido, variável `--lc-*` renomeada |
| **MINOR** (`v1.1.0`) | Algo novo, sem tirar nada | Componente novo estilizado, efeito novo, variável nova |
| **PATCH** (`v1.0.1`) | Correção ou ajuste fino | Hover cortado, espaçamento, contraste, bug em tela pequena |

### Fluxo de release

1. Trabalhe no `dev` e teste com a URL `@dev`.
2. Atualize a versão no comentário do topo de `locadora-retro.css`.
3. Faça o merge de `dev` em `main`, crie a tag e envie:
   ```bash
   git switch main && git merge --ff-only dev
   git tag v1.0.1 && git push origin main v1.0.1
   ```
4. Tags nunca são movidas nem recriadas. Se algo saiu errado, corrija e lance uma versão nova.

URLs de branch e de faixa (`@1`) ficam em cache no jsDelivr por algumas horas. Para forçar a atualização, abra a mesma URL trocando `cdn.jsdelivr.net` por `purge.jsdelivr.net`. URLs de versão fixa não têm esse problema.

### Notas para quem for editar

- O tema base do UNIT3D define `html { font-size: 10px }`, ou seja, 1rem = 10px. No bloco "Camada LOCADORA" (os efeitos visuais do tema), use **px**.
- O bloco "Layout (herdado)" vem de um CSS anterior e usa `rem` calibrado nessa escala.
- As cores dos adesivos do Random Media dependem dos IDs de categoria do site (`/similar/{id}.`). Os valores atuais são Séries = 2 e Animes = 6; ajuste para os IDs do seu site.
- O texto da bolinha do pôster fica na variável `--lc-poster-sticker`.
