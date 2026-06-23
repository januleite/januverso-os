# JANUVERSO OS

Sistema operacional pessoal — Janu Leite.
PWA leve, offline-first, sem backend. Dados ficam no `localStorage` do navegador.

## Arquivos

```
januverso-os/
├── index.html              # o app inteiro (HTML + CSS + JS num único arquivo)
├── manifest.webmanifest    # PWA manifest (pra instalar como app)
├── sw.js                   # service worker (cache offline + installability)
├── icon.svg                # ícone do app
└── README.md               # este arquivo
```

## Como subir no GitHub Pages

1. Cria um repo novo (ex: `januverso-os`) — pode ser **público** ou **privado** (Pages funciona em privado se você tem GitHub Pro).
2. Joga os 4 arquivos no repo (`index.html`, `manifest.webmanifest`, `sw.js`, `icon.svg`).
3. Vai em **Settings → Pages**.
4. Em **Source**, escolhe **Deploy from a branch**.
5. Branch: `main`, pasta: `/ (root)`. Salva.
6. Aguarda ~1 min. A URL fica algo como `https://januleite.github.io/januverso-os/`.

## Como instalar no celular (vira app)

### iPhone (Safari)
1. Abre a URL no **Safari** (não funciona no Chrome do iOS pra instalar).
2. Toca no botão **Compartilhar** (quadradinho com seta pra cima).
3. Rola e toca em **"Adicionar à Tela de Início"**.
4. Confirma. O ícone aparece na home.

### Android (Chrome)
1. Abre a URL no Chrome.
2. Vai aparecer um banner "Adicionar à tela inicial" ou um menu (3 pontinhos) → **Instalar app**.
3. Confirma. Vira um app nativo, abre em tela cheia.

## Como instalar no Mac/PC (desktop também vira app)

- **Chrome / Edge**: ícone de instalação na barra de endereço (canto direito) → "Instalar JANUVERSO OS".
- **Safari (Mac)**: Arquivo → Adicionar ao Dock.

## Backup e migração entre dispositivos

Como os dados ficam no `localStorage` (por navegador, por dispositivo), use:

- **↓ backup** no header — baixa um JSON com tudo (`januverso-backup-YYYY-MM-DD.json`)
- **↑ restaurar** no header — carrega um JSON e substitui os dados atuais

Recomendação: backup semanal, salvo no Drive (em `00_DASHBOARD/backups/januverso/` por exemplo).

## Como editar / customizar

Tudo está em `index.html`. Estrutura:

- **`:root` CSS variables** (linha ~25): paleta de cores. Mexe aí pra trocar visual.
- **`defaultState()`** (procura no JS): dados iniciais (projetos pré-carregados). Edita aí pra mudar seeds.
- **`ABAS`** (linha ~860 aprox.): seções do app. Adiciona/remove abas alterando esse array.

## Próximos passos possíveis (quando fizer sentido)

- **Sincronizar entre dispositivos**: trocar `localStorage` por Supabase ou Firebase. Já fica multi-device + multi-sessão.
- **Conectar ao MAESTRO AI**: criar endpoint no MAESTRO que lê o JSON do JANUVERSO OS — daí o copiloto sugere prioridades baseado no que você tem em aberto.
- **Notificações**: web push pra hábitos diários (caminhada, leitura).
- **Modo família/equipe**: namespacing por usuário (depois de Supabase).

## Stack

- HTML5 + CSS vanilla + JS vanilla (zero dependências, zero build step)
- Web Storage API (`localStorage`)
- PWA (Service Worker + Manifest)
- Google Fonts: Fraunces, Inter, JetBrains Mono

Sem framework. Sem npm install. Sem build. Abre e roda.

---

Feito com Claude · brega elegante · do Agreste ao Grammy.
