# LP Grupo VIP — Black Friday AF Moda Fitness Rio Preto

Página estática (HTML + CSS + JS puro), sem build e sem backend.

## 1. Antes de publicar

| O quê | Onde | Como |
|---|---|---|
| Link do Grupo VIP | `config.js` → `grupoVip` | Cole o link de convite do WhatsApp. Todos os botões usam esse link. |
| Meta Pixel | `config.js` → `metaPixelId` | Cole só os números do ID. Vazio = Pixel desligado. |
| Domínio | `index.html`, `robots.txt`, `sitemap.xml` | Substitua `SEU-DOMINIO.com.br` pelo domínio final (buscar e substituir). |

## 2. Meta Pixel

- `PageView` dispara ao abrir a página (se houver ID).
- `Lead` dispara no clique em qualquer botão do Grupo VIP, **uma única vez por sessão** (sem duplicar se a pessoa clicar em vários botões ou voltar para a página na mesma aba).
- Parâmetros enviados: `content_name: "Grupo VIP Black Friday"`, `content_category: "Live Shopping 26/11"` e `cta` (hero, convite, final ou fixo).

## 3. Publicação

**Vercel:** importe a pasta (ou arraste em vercel.com/new) → Deploy. Em *Settings → Domains*, adicione o domínio e configure o DNS indicado (registro A `76.76.21.21` ou CNAME `cname.vercel-dns.com`). O `vercel.json` já define cache das imagens.

**Netlify:** arraste a pasta em app.netlify.com/drop. Em *Domain management*, adicione o domínio. O `netlify.toml` já está pronto.

**Hospedagem comum (Hostinger, cPanel etc.):** envie todos os arquivos para `public_html`.

## 4. Depois de publicar

- Teste o link de compartilhamento no WhatsApp e em https://developers.facebook.com/tools/debug/ (força a atualização da imagem `og-image.jpg`).
- Confira o Pixel com a extensão Meta Pixel Helper ou em *Gerenciador de Eventos → Testar eventos*.

## Estrutura

```
index.html          página
config.js           link do grupo + Pixel
img/                fotos otimizadas (WebP, 640 e 1080 px)
logo-af-dourado.png logo com fundo transparente
og-image.jpg        imagem de compartilhamento 1200×630
favicon-af.png, apple-touch-icon.png
vercel.json, netlify.toml, robots.txt, sitemap.xml
```
