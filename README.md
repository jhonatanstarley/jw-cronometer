# ⏱ JW Cronômetro

Cronômetro web para discursos das Testemunhas de Jeová. Roda 100% no navegador, sem backend, sem dependências externas — instale como PWA direto na tela inicial do celular.

---

## ✨ Funcionalidades

- **Sessões personalizáveis** — defina nome e duração para cada parte do discurso (Introdução, Pontos, Conclusão etc.)
- **Presets rápidos** — atalhos para formatos comuns (30, 45, 60 min)
- **Alertas sonoros** — bipes ao final de cada sessão e ao encerrar o discurso
- **Flash visual (acessibilidade)** — overlay transparente cobre toda a tela: verde ao fim de cada sessão intermediária, vermelho ao encerrar o discurso; não ofusca o conteúdo e não bloqueia interações — ideal para deficientes auditivos
- **Anel de progresso** — visualização circular do tempo restante com indicação de sessão atual
- **Lista de sessões ao vivo** — acompanhe qual parte está em andamento e o horário de conclusão de cada uma
- **Pausar / Retomar** — interrompa o cronômetro sem perder o estado
- **Persistência em background** — ao reabrir o app o cronômetro é restaurado corretamente mesmo que o dispositivo tenha ficado em segundo plano
- **Wake Lock** — impede que a tela apague enquanto o timer está rodando (navegadores compatíveis)
- **PWA instalável** — banner de instalação nativo; funciona offline após a primeira visita
- **Compatível com iOS e Android** — suporte a safe-area, apple-touch-icon e manifest gerado dinamicamente

---

## 🚀 Deploy

### Vercel (recomendado)

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/jw-cronometro.git
cd jw-cronometro

# 2. Deploy com a CLI da Vercel
npx vercel
```

Ou conecte o repositório direto no painel em [vercel.com](https://vercel.com) — zero configuração necessária além do `vercel.json` já incluso.

### Netlify / GitHub Pages / qualquer CDN estático

Basta publicar o arquivo `index.html` na raiz. Não há build step nem servidor necessário.

---

## 📁 Estrutura

```
/
└── index.html   # App completo (HTML + CSS + JS em arquivo único)
└── vercel.json  # Configuração de headers e roteamento para Vercel
└── README.md
```

---

## 🛠 Desenvolvimento local

Nenhuma dependência para instalar. Abra diretamente no navegador:

```bash
# Opção 1 — abrir o arquivo direto
open index.html

# Opção 2 — servidor local simples (recomendado para testar PWA/Wake Lock)
npx serve .
# ou
python3 -m http.server 8080
```

> **Dica:** Wake Lock e o prompt de instalação PWA exigem HTTPS. Em desenvolvimento use `localhost` (já é tratado como contexto seguro pelos navegadores) ou um túnel como `npx localtunnel`.

---

## 📱 Instalar como PWA

1. Acesse a URL do deploy pelo celular
2. O banner de instalação aparecerá automaticamente (Android/Chrome)
3. No iOS: toque em **Compartilhar → Adicionar à Tela de Início**

---

## 🧩 Tecnologias

| Recurso | Detalhe |
|---|---|
| Fontes | Google Fonts — Noto Serif + Noto Sans |
| Ícones / Manifest | Gerados dinamicamente via Canvas API |
| Áudio | Web Audio API (osciladores) |
| Persistência | `localStorage` |
| Tela ligada | Screen Wake Lock API |
| Instalação | PWA / beforeinstallprompt |

---

## 📄 Licença

MIT — use, modifique e distribua livremente.
