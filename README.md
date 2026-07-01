# nicolaslopes.dev

Site pessoal de Nícolas Tomaschewski Lopes — construído com [Hugo](https://gohugo.io/).

---

## Executar localmente

**Requisitos:** Hugo Extended v0.120+

```bash
# Instalar Hugo (Linux)
curl -L https://github.com/gohugoio/hugo/releases/latest/download/hugo_extended_Linux-64bit.tar.gz \
  | tar -xz -C ~/.local/bin hugo

# Clonar e iniciar
git clone <url-do-repositório>
cd Blog
hugo server --buildDrafts
```

O site estará disponível em `http://localhost:1313`.

`--buildDrafts` inclui posts com `draft: true` — remova a flag para ver apenas o conteúdo publicado.

### Criar novo conteúdo

```bash
# Artigo de blog
hugo new content blog/tecnologia/meu-artigo.md

# Projeto
hugo new content projetos/meu-projeto.md

# Nota
hugo new content notas/minha-nota.md
```

Após escrever, mude `draft: true` para `draft: false` no frontmatter para publicar.

---

## Deploy via GitHub Actions

O workflow em `.github/workflows/deploy.yml` publica automaticamente no GitHub Pages a cada push para `main`.

**Configuração inicial:**

1. No repositório GitHub, vá em **Settings → Pages**
2. Em **Source**, selecione **GitHub Actions**
3. Faça push para `main` — o workflow será executado automaticamente

**Variáveis importantes:**
- Atualize `baseURL` em `hugo.toml` para a URL real do site (ex: `https://seuusuario.github.io/Blog/` ou domínio customizado)
- Para domínio customizado, adicione o arquivo `static/CNAME` com o domínio

---

## Deploy via Cloudflare Pages

1. No painel da Cloudflare, acesse **Workers & Pages → Create application → Pages**
2. Conecte o repositório GitHub
3. Configure o build:
   - **Framework preset:** Hugo
   - **Build command:** `hugo --minify`
   - **Build output directory:** `public`
   - **Environment variable:** `HUGO_VERSION` = `0.147.9`
4. Clique em **Save and Deploy**

Deploys subsequentes acontecem automaticamente a cada push para `main`.

Para domínio customizado: **Custom domains → Add custom domain** no painel do projeto.

---

## Estrutura do projeto

```
.
├── archetypes/          # Templates para novo conteúdo
├── assets/
│   ├── css/main.css     # Estilo principal
│   └── js/theme-toggle.js
├── content/
│   ├── sobre.md
│   ├── contato.md
│   ├── projetos/
│   ├── blog/
│   │   ├── engenharia/
│   │   ├── tecnologia/
│   │   ├── reflexoes/
│   │   └── leituras/
│   └── notas/
├── layouts/             # Templates Hugo
│   ├── _default/
│   ├── partials/
│   ├── projetos/
│   └── notas/
├── static/              # Arquivos estáticos (favicon, etc.)
└── hugo.toml            # Configuração principal
```
