# Franquias The Hair Bar

Página de captação de franqueados da The Hair Bar Escovaria. Site estático (HTML, CSS e JS puros), sem build.

## Estrutura

```
index.html          página principal
404.html            página de erro
netlify.toml        configuração do Netlify (cache e cabeçalhos)
robots.txt
og.jpg              imagem de compartilhamento (WhatsApp, redes sociais)
favicon.png
img/
  logo.webp
  prod1–6.webp      linha Easy Style
  unidade/          fotos reais da unidade conceito
```

## Publicar no GitHub

1. Crie um repositório (ex.: `franquias-thehairbar-site`).
2. Envie todo o conteúdo desta pasta para a raiz do repositório, incluindo `.gitignore` e `netlify.toml`.

```bash
git init
git add .
git commit -m "Site de franquias The Hair Bar"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/franquias-thehairbar-site.git
git push -u origin main
```

## Publicar no Netlify

1. Netlify → **Add new site → Import an existing project → GitHub** e escolha o repositório.
2. Build command: deixe em branco. Publish directory: `.` (já definido no `netlify.toml`).
3. Deploy. Cada `git push` na `main` publica uma nova versão.

### Receber os leads (Netlify Forms)

Os dois formulários (`franqueado-topo` e `franqueado-rodape`) já estão marcados para o Netlify Forms.

1. Em **Forms**, clique em **Enable form detection** e faça um novo deploy.
2. Em **Forms → Form notifications**, adicione um aviso por e-mail (ex.: `franquias@thehairbar.com.br`).
3. Teste enviando um cadastro pelo site publicado.

Depois de enviar, o candidato vê um botão que abre o WhatsApp da expansão com os dados já preenchidos.

## Conectar o domínio da The Hair Bar

Sugestão de endereço: `franquias.thehairbar.com.br`.

1. Netlify → **Domain management → Add a domain** → digite o subdomínio.
2. No painel DNS onde o domínio `thehairbar.com.br` está registrado, crie um registro:
   - Tipo: `CNAME`
   - Nome: `franquias`
   - Valor: `NOME-DO-SITE.netlify.app`
3. Aguarde a propagação (minutos a algumas horas). O Netlify emite o HTTPS sozinho.

Se for usar o domínio principal (`thehairbar.com.br`), siga as instruções de registro A/ALIAS que o Netlify mostrar.

### Depois de definir o domínio

No `<head>` do `index.html`, troque a imagem de compartilhamento para o endereço completo e adicione o canônico:

```html
<meta property="og:image" content="https://franquias.thehairbar.com.br/og.jpg">
<meta property="og:url" content="https://franquias.thehairbar.com.br/">
<link rel="canonical" href="https://franquias.thehairbar.com.br/">
```

## Editar conteúdo

- **Números e formatos**: seções `stats` e `investimento` do `index.html`.
- **Depoimento**: bloco `<blockquote>` da seção "A marca" (há um comentário indicando onde trocar).
- **Fotos do carrossel**: pasta `img/unidade/`. Para incluir uma foto, copie um `<figure class="slide ...">` do carrossel. Use a classe `l` para foto horizontal e `p` para vertical.
- **Contato e WhatsApp**: número `5511920915958` aparece no rodapé, no botão flutuante e na variável `WA` do script.
