# 🚀 Guia Completo de Deploy – SNA Soluções em Negócios Ambientais

Este documento contém todas as instruções necessárias para publicar o site da **SNA** na web com alto desempenho, segurança (SSL) e suporte a domínio personalizado (`snaconsult.com.br`).

---

## 📁 Estrutura de Arquivos para Produção

O projeto foi totalmente organizado para ser servido como um site estático moderno de altíssima performance (HTML, CSS puro e JavaScript nativo):

```text
SNA/
├── index.html                   # Página principal de produção (Servida na raiz /)
├── indexv3.html                 # Cópia de segurança / desenvolvimento v3
├── assets/                      # Imagens de fundo, fotos e ilustrações
│   ├── sunrise-bali-jungle.jpg
│   ├── artistic-blurry-colorful-wallpaper-background.jpg
│   ├── consultoria ambiental.jpg
│   ├── laboratório de analise ambiental.webp
│   ├── Gerenciadoras de resíduos.jpg
│   └── Empresas de engenharia ambiental.jpg
└── extracted/                   # Logotipos vetoriais SVG oficiais
    └── SVG/
        ├── Logo Transparente Branco.svg
        └── Logo Transparente Verde.svg
```

---

## 🌐 Opções de Hospedagem Recomendadas

### Opção 1: Vercel (Recomendado – Gratuito e Ultrarrápido)

1. Crie uma conta em [Vercel.com](https://vercel.com/).
2. Instale o Vercel CLI no terminal ou conecte sua conta do GitHub/GitLab:
   ```bash
   npx vercel
   ```
3. Siga as instruções no terminal (selecione o diretório raiz do projeto).
4. **Pronto!** A Vercel fornecerá uma URL `https://sna-xxxx.vercel.app` instantaneamente com certificado SSL grátis.

---

### Opção 2: Netlify (Arrastar e Soltar – 1 Minuto)

1. Acesse [Netlify.com](https://www.netlify.com/) e faça login.
2. Na aba **Sites**, escolha a opção **"Add new site"** > **"Deploy manually"**.
3. Arraste a pasta inteira do projeto `SNA` para a área de upload.
4. O site estará no ar em segundos com suporte automático a HTTPS.

---

### Opção 3: Hospedagem Tradicional (Hostinger / cPanel / KingHost / Locaweb)

1. Acesse o painel **cPanel** ou o Gerenciador de Arquivos da sua hospedagem.
2. Navegue até a pasta `public_html` ou `www`.
3. Faça o upload dos seguintes arquivos e pastas:
   - `index.html`
   - Pasta `assets/`
   - Pasta `extracted/`
4. Acesse o seu domínio (ex: `https://snaconsult.com.br`) para verificar.

---

## 📩 Configuração do Formulário de Contato

O formulário de contato na **Dobra 8** (`#contato`) está pronto para integração com o serviço gratuito [Formspree](https://formspree.io/) ou [Web3Forms](https://web3forms.com/):

1. Crie uma conta gratuita em [Formspree.io](https://formspree.io/).
2. Crie um novo formulário e copie o seu `Form ID` (ex: `f/xwyzpqab`).
3. No arquivo `index.html` (linha ~3180), atualize a tag `<form>`:
   ```html
   <form action="https://formspree.io/f/SEU_FORM_ID" method="POST" id="contactForm">
   ```
4. As mensagens enviadas pelos clientes no site serão entregues diretamente no e-mail `suzuki@snaconsult.com.br`.

---

## 🏷️ Configuração de Domínio Próprio (DNS)

Para apontar o seu domínio corporativo (ex: `snaconsult.com.br`) para a Vercel/Netlify:

| Tipo | Nome / Host | Valor / Destino |
| :--- | :--- | :--- |
| **A** | `@` | `76.76.21.21` *(Vercel)* ou `75.2.60.5` *(Netlify)* |
| **CNAME** | `www` | `cname.vercel-dns.com` ou `SEU-SITE.netlify.app` |

---

## ✅ Checklist Pré-Lançamento

- [x] HTML semântico e responsivo (Mobile, Tablet, Desktop).
- [x] Otimização de imagens e backgrounds.
- [x] Links internos ancorados (`#frentes`, `#quem-somos`, `#para-quem`, `#metodologia`, `#planos`, `#contato`).
- [x] Suporte a Open Graph para compartilhamento no WhatsApp e LinkedIn.
- [x] Remoção do WhatsApp flutuante e inclusão do logotipo verde da SNA.
