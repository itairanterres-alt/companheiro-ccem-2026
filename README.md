# Companheiro CCEM 2026

Aplicativo web mobile-first do **12º Congresso Catarinense de Endocrinologia e Metabologia**.

🗓️ 23 e 24 de outubro de 2026
📍 Expoville · Joinville-SC
🏛️ Realização: SBEM-SC

## O que faz

Aplicativo do programa vivo do congresso, com captura individual como acessório.

### Onda 1 — Programa Vivo

- **Linha do tempo do dia** — barra visual com todas as sessões e a marca "agora"
- **Acontecendo agora** — strip superior com contexto temporal automático
- **Marcação de interesse + lembrete** — toggle no card, notificação no navegador
- **Mini-bio do palestrante** — toque no nome para abrir modal com bio
- **Briefing pré-sessão** — 3 pontos de contexto curados antes da palestra
- **Quiz preparatório opcional** — questões geradas por IA, sem nota
- **Mapa do Expoville** — modal acessível pelo header do programa
- **Captura como acessório** — botão dentro do painel expansível, não mais em destaque

### Trilhas paralelas (não no app principal)

- Plataforma de submissão de pôsteres digitais — projeto irmão
- Anais oficial com DOI/ISBN — em discussão institucional

## Estado atual

Conteúdo das bios, briefings e quizzes está em **modo curadoria**: parte com texto-placeholder, parte com conteúdo de exemplo. Tudo será revisado pela Comissão Científica antes do evento.

## Pontos de troca para produção

`// TODO: integrar com API real` marca cada ponto no código:

1. `getMockReply()` → chamada real à API Gemini 2.0 Flash
2. `loadState()` / `saveState()` → Supabase para sincronização entre dispositivos
3. `getOrCreateUserId()` → integração com sistema de inscrição da Promotes
4. `sendPhoto()` / `finalizeRecording()` → análise multimodal via Gemini
5. `exportPDF()` → gerador real (jsPDF ou server-side)
6. `PROGRAM_DAYS`, `SESSION_META`, `SPEAKER_BIOS` → carregar do banco
7. Notificações reais → service worker com push (pós-Onda 1)

## Stack

- **Frontend**: HTML/CSS/JS vanilla, standalone, sem build
- **Tipografia**: Fraunces + DM Sans + JetBrains Mono (Google Fonts)
- **Hospedagem**: Vercel (deploy automático via GitHub)
- **Banco (produção)**: Supabase
- **IA (produção)**: Gemini 2.0 Flash (multimodal)

## Como rodar localmente

Abra o `index.html` no navegador. Sem dependências locais.

## Como atualizar

1. Editar `index.html` no GitHub (botão de lápis)
2. Commit
3. Vercel re-deploya em ~10s, URL não muda

---

Coordenação: Dr. Itairan da Silva Terres — Comissão Científica CCEM 2026
