# JohnDev portfolio

Responsive English-language Roblox portfolio for https://johndevrbx.github.io.

## Publish
Create the public repository `johndevrbx/johndevrbx.github.io`, upload this directory's contents (including `.github` and `.nojekyll`), and choose GitHub Actions in Settings → Pages. The included workflow publishes changes to main.

## Editing panel — authentication setup still required
`/admin/` contains Decap CMS, configured for the repository above. Production GitHub login requires a trusted OAuth authentication service; it is not provided by GitHub Pages or the Codex GitHub integration. Choose and configure an OAuth provider using https://decapcms.org/docs/github-backend/ and set its backend configuration in `admin/config.yml`. Do not commit credentials. The editor must not be considered operational until a sign-in and a publish test pass.

For local editing, serve this folder with `python -m http.server 8765`, run `npx decap-server` from this directory in a separate terminal, then open http://localhost:8765/admin/. `local_backend: true` enables the development proxy; remove it for production after OAuth is configured.

In Portfolio → Projects, add a title, category, descriptions, cover and repeatable media. Use image for images, video for direct MP4 files, and youtube for YouTube links. Save/publish updates the JSON content and triggers deployment. Featured items sort first on Home. Unpublished entries are hidden in the UI but remain in the public repository and JSON: do not store confidential drafts here.

## Content
No client projects, testimonials or experience claims have been invented. The portfolio starts empty. All category pages read `content/portfolio.json`. Copy this shape into its projects list if editing without the panel:

```json
{"title":"Your actual project","category":"systems","summary":"A short introduction","description":"Your role and how the system works.","cover":"/assets/uploads/cover.webp","featured":true,"published":true,"link":"","media":[{"type":"image","url":"/assets/uploads/screenshot.webp","caption":"A descriptive caption"},{"type":"youtube","url":"https://www.youtube.com/watch?v=YOUR_VIDEO_ID","caption":"Gameplay demonstration"}]}
```

Categories: systems, vfx, buildings, animations. Images and video captions support accessible galleries. For large videos use an external video host to avoid exhausting GitHub Pages storage. The avatar was supplied by JohnDev. Contact currently links to the supplied GitHub profile; add other contact details when provided.

## Preview
Run `python -m http.server 8765` in this folder. Open http://localhost:8765. No site build or package installation is needed.
## Editor local simplificado

Abra http://127.0.0.1:8765/editor/ no Chrome ou Edge do computador. Clique em Selecionar pasta do portfólio e escolha esta pasta `johndev-portfolio`. Permita a gravação quando o navegador solicitar.

Para adicionar um trabalho: clique em Novo trabalho, escreva título e descrições em inglês, escolha a categoria e a capa, adicione várias imagens ou vídeos MP4/WebM e/ou links do YouTube, e clique em Salvar trabalho. Atualize a página do portfólio. As mídias são copiadas automaticamente para assets/uploads e a lista de trabalhos é gravada em content/portfolio.json.

Para editar: selecione um trabalho na lista, altere os campos e salve antes de selecionar outro. Em Perfil, contato e redes, você pode alterar Discord, apresentação, serviços, pagamentos e redes sociais, depois clicar em Salvar perfil e redes. As informações ficam em content/settings.json.

O editor usa o seletor de pasta do navegador. Ele não precisa de login no GitHub e não publica automaticamente. Ele precisa de um navegador compatível com acesso à pasta local e do servidor local em execução. O painel /admin/ continua sendo a opção de edição online com autenticação a configurar.

## Destaques e fundo da Home
No editor local, conecte a pasta e encontre Mídias em destaque na Home. Os três destaques aceitam imagens ou vídeos MP4/WebM e legendas em inglês. O campo Vídeo de fundo aceita um clipe curto MP4/WebM, reproduzido sem som e em repetição atrás da apresentação. Use Salvar perfil e redes para gravar os destaques e o fundo. Remover vídeo de fundo e Limpar destaque só são confirmados ao salvar.

Sem mídias configuradas, os espaços mostram placeholders identificados. Não são trabalhos de demonstração. O botão Pause motion pausa as animações decorativas e o vídeo de fundo; vídeos dos destaques têm controles próprios. O site respeita a preferência do sistema por movimento reduzido.

Após hospedar, continue editando a mesma pasta local e envie as alterações ao repositório para atualizar o site. Alterar arquivos locais não altera automaticamente o site publicado.
