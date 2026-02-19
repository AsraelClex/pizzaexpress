# 🛒 Telegram SaaS - Negozi Multi-Client

## Struttura

```
telegram-saas/
├── admin.html      ← Pannello Admin (TUO)
├── shop.html       ← Template Negozio (per tutti i clienti)
├── config.json     ← Configurazione (DA MODIFICARE)
└── README.md
```

---

## 🚀 Quick Start

### Step 1: Pubblica su GitHub Pages

1. Crea un repository su GitHub
2. Carica questi file
3. Vai su Settings → Pages
4. Attiva GitHub Pages (main branch)
5. Ottieni il tuo link: `tuonome.github.io/nome-repo`

### Step 2: Configura

Apri `config.json` e modifica:

```json
{
  "shopName": "Il Mio Negozio",
  "productsUrl": "https://docs.google.com/spreadsheets/d/e/.../pub?output=csv",
  "adminChatId": "TUO_CHAT_ID"
}
```

### Step 3: Crea Google Sheets

Crea un foglio Google con questo formato:

| A | B | C | D |
|---|---|---|---|
| Nome | Prezzo | Immagine | Descrizione |
| Maglietta | 19.90 | https://... | Cotone |

**Importante:** Pubblica il foglio come CSV:
- File → Pubblica sul web → CSV

### Step 4: Collega al Bot

Nel tuo bot Telegram:

```javascript
bot.command('negozio', async (ctx) => {
    await ctx.reply('🛒 Il nostro negozio:', {
        reply_markup: {
            inline_keyboard: [[
                { text: '🛒 APRI NEGOZIO', web_app: { url: 'https://tuonome.github.io/repo/shop.html' } }
            ]]
        }
    });
});
```

---

## 👥 Per Aggiungere Nuovi Clienti

1. Apri `admin.html` sul tuo telefono/PC
2. Clicca **➕ AGGIUNGI NUOVO NEGOZIO**
3. Inserisci:
   - Nome negozio
   - Username Telegram cliente
   - Nome proprietario
4. Clicca **CREA**
5. Invia al cliente il link del suo negozio

---

## 📦 Come Ogni Cliente Gestisce i Suoi Prodotti

Il cliente deve creare il proprio Google Sheets con i suoi prodotti, poi te lo comunica e tu aggiorni il config.

**Oppure** (versione avanzata): ogni cliente ha la propria configurazione separata.

---

## 💰 Prezzo che Puoi Chiedere

- **Setup iniziale**: €49-99
- **Gestione mensile**: €9-19/mese
- **Dominio custom**: +€10/mese

---

## 🔒 Privacy

- Hosting: GitHub Pages (zero tracking)
- Dati: Google Sheets (tu controlli)
- Zero costi mensili!
