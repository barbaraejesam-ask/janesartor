# Jane Sartor — Mentora e Terapeuta Holística

Site estático (HTML único, sem build). Funciona direto no Vercel, sem configurar framework.

## O que tem na pasta

| Arquivo | Para que serve |
|---|---|
| `index.html` | O site inteiro: CSS, JS e **todas as imagens (logo, foto e pedras) já embutidas**. Funciona sozinho, sem depender de outros arquivos de imagem |
| `imagens-originais/` | Cópias da logo e da foto, nos tamanhos usados e nos originais. **O site não usa esta pasta**; ela fica guardada para futuras trocas |
| `vercel.json` | Configuração do Vercel: URLs limpas, cabeçalhos de segurança, cache |
| `404.html` | Página de erro no mesmo estilo do site |
| `favicon.svg` e `favicon.png` | Ícone da aba do navegador |
| `apple-touch-icon.png` | Ícone quando alguém salva o site na tela inicial do celular |
| `og-image.jpg` | Imagem que aparece quando o link é enviado no WhatsApp, Instagram etc. |
| `robots.txt` | Permite que o Google indexe o site |
| `.gitignore` | Evita subir arquivos de sistema para o GitHub |

> **Importante:** as imagens do site estão dentro do `index.html`. Mesmo assim, suba todos os arquivos da pasta: o `vercel.json`, o `404.html`, os ícones e o `og-image.jpg` também são usados.

## 1. Subir para o GitHub

### Pelo navegador (sem terminal)

1. Entre em [github.com/new](https://github.com/new).
2. Nome do repositório: `site-jane-sartor` (ou o que você já usa). Deixe **Public** ou **Private** (o Vercel funciona com os dois).
3. **Não** marque "Add a README" (já existe um aqui).
4. Clique em **Create repository**.
5. Na tela seguinte, clique em **uploading an existing file**.
6. Arraste **todos os arquivos desta pasta** (inclusive `.gitignore`, que pode estar oculto no seu computador).
7. Clique em **Commit changes**.

### Pelo terminal

```bash
cd pasta-do-site
git init
git add .
git commit -m "Site Jane Alair"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/site-jane-sartor.git
git push -u origin main
```

## 2. Publicar no Vercel

1. Entre em [vercel.com](https://vercel.com) e faça login com o GitHub.
2. Clique em **Add New → Project**.
3. Escolha o repositório `site-jane-alair` e clique em **Import**.
4. Em **Framework Preset**, deixe **Other**. Não preencha *Build Command* nem *Output Directory*.
5. Clique em **Deploy**. Em cerca de 30 segundos o site está no ar em `https://site-jane-alair.vercel.app` (ou similar).

## 3. Trocar o endereço de exemplo (importante)

Depois do primeiro deploy, o Vercel mostra o endereço real do site. No arquivo `index.html`, procure por:

```
SEU-DOMINIO.vercel.app
```

Ele aparece em 3 linhas (`canonical`, `og:url` e `og:image`), logo no início do arquivo. Troque pelo endereço real, sem `https://` e sem barra no final, por exemplo `site-jane-alair.vercel.app`.

Se você já trocou esse endereço numa versão anterior, faça a troca de novo neste `index.html` novo.

Sem essa troca o site funciona normalmente, mas o link **não mostra a imagem de prévia** ao ser compartilhado no WhatsApp.

Para testar a prévia depois de trocar: [opengraph.xyz](https://www.opengraph.xyz). O WhatsApp guarda cache de prévias, então links já enviados antes da troca podem continuar sem imagem.

## 4. Domínio próprio (opcional)

1. No Vercel, abra o projeto → **Settings → Domains**.
2. Digite o domínio (ex.: `janealair.com.br`) e clique em **Add**.
3. O Vercel mostra os registros DNS para configurar onde o domínio foi comprado (Registro.br, GoDaddy etc.). Leva de alguns minutos a algumas horas.
4. Depois de ativo, repita o passo 3 acima usando o domínio novo.

## Como atualizar o site depois

Qualquer alteração enviada ao GitHub publica automaticamente em cerca de 30 segundos.

- **Pelo navegador:** abra o arquivo no repositório → ícone de lápis → edite → **Commit changes**.
- **Pelo terminal:** `git add . && git commit -m "ajuste" && git push`

## Como trocar a foto ou a logo

Como as imagens ficam dentro do `index.html`, a troca exige reembutir a imagem. O jeito mais simples é enviar a nova imagem para o Claude e pedir para atualizar o site.

Se preferir fazer sozinha:
1. Prepare a imagem no tamanho de uso: foto com cerca de 640 px de largura (JPEG) e logo com cerca de 560 px de largura (PNG com fundo transparente).
2. Converta para base64 em qualquer conversor online ("imagem para base64").
3. No `index.html`, procure por `<img src="data:image/` e troque o texto longo que vem depois de `base64,` pelo novo código.

## Onde ficam os dados de contato

Procure no `index.html` (Ctrl+F):

- **WhatsApp:** `5548988367769` (aparece em 2 lugares: botão de contato e botão flutuante). Formato: `55` + DDD + número.
- **Instagram:** `janedebonasartorterapoas` (rodapé).

## Pendências de conteúdo do site

- Nome da marca: o site passou a usar "Jane Sartor — Mentora e Terapeuta Holística", conforme a logo nova. Confirmar com a Jane se este é o nome definitivo.
- Seção de depoimentos: ainda não incluída, aguardando autorização de uso de imagem e texto das clientes.
- Preços: não são exibidos no site, por decisão do Encontro 2.
- O site ainda não incorpora o "Caderno da Transformação" nem os novos modelos de post do Instagram. Isso está previsto para a reunião final de validação.
