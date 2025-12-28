# 🎫 Discord Ticket System Bot

Ein professionelles, vollständig anpassbares Ticket-System für Discord mit umfangreichen Features und persistenten Buttons.

## ✨ Features

### 🎯 Kern-Funktionen
- ✅ **Dynamische Ticket-Typen** - Unbegrenzt viele Ticket-Kategorien erstellen
- 🔄 **Zwei Modi**: Channels oder Threads
- 🎭 **Join-System**: Ping-Modus oder Join-Button für Supporter
- 📝 **Modals**: Optional anpassbare Formulare mit bis zu 5 Feldern
- 🔒 **Claim-System**: Tickets können von Supportern übernommen werden
- 📊 **Transcript-System**: Automatische HTML-Transcripts mit GitHub Pages Upload
- 💬 **DM-Benachrichtigungen**: Automatische Benachrichtigung an Ticketersteller
- 🔢 **Ticket-IDs**: Fortlaufende Nummerierung für bessere Übersicht
- 🎨 **Vollständig anpassbar**: Embeds, Farben, Texte, Buttons

### 🚀 Erweiterte Features
- ⚡ **Persistent Views**: Buttons funktionieren nach Bot-Restart
- 🗂️ **Datenbank-Verwaltung**: Bereinigung alter Ticket-Daten
- 📈 **Logging**: Ausführliche Logs für alle Ticket-Aktionen
- 🔐 **Berechtigungssystem**: Flexible Rollen-basierte Zugriffssteuerung
- ⏱️ **Close-Request**: Zeitverzögertes Schließen mit Abbruch-Option
- 🏷️ **Ticket-Management**: Add/Remove User, Rename, Transfer, AFK-Markierung

---

## 🎮 Setup-Anleitung

### Schnell-Setup (Empfohlen)
```
/ticket_interactive_setup
```
Interaktives Setup mit allen Optionen in einem Interface.

### Schritt-für-Schritt Setup

#### 1. Basis-Konfiguration
```
/ticket_setup
  category: #tickets (Kategorie für Ticket-Channels)
  log_channel: #ticket-logs (Log-Channel)
  ticket_channel: #create-ticket (Channel für Buttons)
```

#### 2. Ticket-Typ hinzufügen
```
/ticket_type_add
  name: Support
  button_label: Support erhalten
  role: @Support-Team
  button_emoji: 🎫
  use_modal: False
```

#### 3. Optional: Modal-Felder hinzufügen
```
/ticket_field_add
  ticket_type: Support
  label: Dein Problem
  style: paragraph
  required: True
```

#### 4. Modi einstellen

**Ticket-Modus wählen:**
```
/ticket_mode
  mode: Channel oder Thread
```

**Join-Modus wählen:**
```
/ticket_join_mode
  mode: Ping oder Join-Button
```

#### 5. Ticket-System deployen
```
/ticket_deploy
```

---

## 📋 Alle Commands

### 🔧 Setup & Konfiguration

| Command | Beschreibung |
|---------|-------------|
| `/ticket_interactive_setup` | Interaktives Setup mit allen Optionen |
| `/ticket_setup` | Basis-Konfiguration (Kategorie, Log, Channel) |
| `/ticket_type_add` | Neuen Ticket-Typ erstellen |
| `/ticket_type_remove` | Ticket-Typ löschen |
| `/ticket_field_add` | Modal-Feld zu Ticket-Typ hinzufügen |
| `/ticket_mode` | Channel- oder Thread-Modus wählen |
| `/ticket_join_mode` | Ping oder Join-Button Modus |
| `/ticket_deploy` | Ticket-Buttons im Channel posten |
| `/ticket_reset_all` | Komplette Konfiguration zurücksetzen |

### 🎨 Design & Anpassung

| Command | Beschreibung |
|---------|-------------|
| `/ticket_embed_title` | Embed-Titel ändern |
| `/ticket_embed_description` | Embed-Beschreibung ändern |
| `/ticket_embed_color` | Embed-Farbe setzen (Hex) |
| `/ticket_embed_field_add` | Feld zum Embed hinzufügen |
| `/ticket_embed_field_remove` | Feld aus Embed entfernen |
| `/ticket_embed_clear` | Alle Embed-Einstellungen löschen |

### 🔐 Berechtigungen

| Command | Beschreibung |
|---------|-------------|
| `/ticket_claim_roles` | Rollen setzen die Tickets claimen können |
| `/ticket_permissions_set` | Rolle zu Ticket-Typ hinzufügen |
| `/ticket_permissions_remove` | Rolle von Ticket-Typ entfernen |

### 🎫 Ticket-Verwaltung

| Command | Beschreibung |
|---------|-------------|
| `/ticket_close` | Ticket sofort schließen mit Grund |
| `/ticket_closerequest` | Schließanfrage mit Timer |
| `/ticket_add` | User/Rolle zum Ticket hinzufügen |
| `/ticket_remove` | User/Rolle aus Ticket entfernen |
| `/ticket_rename` | Ticket umbenennen |
| `/ticket_transfer` | Ticket weiterleiten |
| `/ticket_afk` | Ticket als AFK markieren |
| `/ticket_warten` | "Warten auf Antwort" Status setzen |

### 📊 Verwaltung & Tools

| Command | Beschreibung |
|---------|-------------|
| `/ticket_list` | Aktuelle Konfiguration anzeigen |
| `/ticket_github_setup` | GitHub Transcript-Upload einrichten |
| `/ticket_github_disable` | GitHub Upload deaktivieren |
| `/clear_database` | Ticket-Datenbank bereinigen (guild/all) |

---

## 🎨 Modi-Erklärung

### Ticket-Modi

#### 📁 Channel-Modus
- Erstellt eigene Text-Channels in einer Kategorie
- Volle Kontrolle über Berechtigungen
- Bessere Organisation bei vielen Tickets
- **Beispiel:** `#support-john-1`

#### 💬 Thread-Modus
- Erstellt Threads in einem Channel
- Übersichtlicher bei wenigen Tickets
- Spart Server-Channels
- **Beispiel:** Thread "Support-john-1"

### Join-Modi

#### 🔔 Ping-Modus
- Supporter werden direkt beim Erstellen gepingt
- Sofortiger Zugriff auf Tickets
- Gut für kleine Teams

#### 🎫 Join-Button-Modus
- Externes Embed mit Join-Button
- Supporter können Tickets selbst annehmen
- Liste der beigetretenen Supporter
- Gut für große Teams

---

## 🔧 GitHub Transcript Setup

### 1. Repository erstellen
```
1. Gehe zu GitHub
2. Erstelle neues Repository (z.B. "ticket-transcripts")
3. Setze es auf "Public"
```

### 2. GitHub Pages aktivieren
```
Settings → Pages → Source: main branch → Save
```

### 3. Personal Access Token erstellen
```
Settings → Developer settings → Personal access tokens → Generate new token
Scope: "repo" (Full control)
```

### 4. Bot konfigurieren
```
/ticket_github_setup
  owner: dein-github-username
  repo: ticket-transcripts
  token: ghp_xxxxxxxxxxxxx
  path: transcripts
```

### 5. Fertig! 🎉
Transcripts sind erreichbar unter:
```
https://dein-username.github.io/ticket-transcripts/transcripts/
```

---

## 📊 Datenstruktur

### ticket_config.json
```json
{
  "guild_id": {
    "category_id": 123456789,
    "log_channel_id": 123456789,
    "ticket_channel_id": 123456789,
    "join_button_channel_id": 123456789,
    "ticket_mode": "channel",
    "join_mode": "ping",
    "ticket_types": {
      "Support": {
        "button_label": "Support erhalten",
        "button_emoji": "🎫",
        "role_id": 123456789,
        "allowed_roles": [123456789],
        "use_modal": true,
        "modal_fields": [
          {
            "label": "Dein Problem",
            "style": "paragraph",
            "required": true
          }
        ]
      }
    },
    "claim_roles": [123456789],
    "embed": {
      "title": "🎫 Support Tickets",
      "description": "Erstelle ein Ticket!",
      "color": "#00ff00",
      "fields": []
    },
    "github": {
      "enabled": true,
      "owner": "username",
      "repo": "repo-name",
      "token": "ghp_xxx",
      "path": "transcripts"
    }
  }
}
```

### ticket_data.json
```json
{
  "guild_id": [
    {
      "user_id": 123456789,
      "ticket_type": "Support",
      "channel_id": 123456789,
      "channel_name": "support-john-1",
      "created_at": "2025-01-01T12:00:00",
      "is_thread": false,
      "ticket_id": 1
    }
  ]
}
```

---

## 🎯 Button-Funktionen

### Im Ticket-Channel

| Button | Funktion | Berechtigung |
|--------|----------|--------------|
| 🔒 Ticket schließen | Öffnet Modal für Grund → Schließt Ticket | Jeder |
| ✋ Claim | Ticket übernehmen | Claim-Rollen |
| 🔓 Freigeben | Ticket wieder freigeben | Claimer |

### Im Join-Button-Channel (Join-Modus)

| Button | Funktion | Berechtigung |
|--------|----------|--------------|
| 🎫 Ticket joinen | Dem Ticket beitreten | Erlaubte-Rollen |

---

## 🔍 Beispiel-Workflow

### Ticket-Erstellung (mit Modal)
```
1. User klickt "Support erhalten"
2. Modal öffnet sich mit Feldern
3. User füllt Felder aus
4. Ticket wird erstellt: "support-john-1"
5. Support-Team wird gepingt
```

### Ticket-Bearbeitung
```
1. Supporter klickt "Claim"
2. Ticket wird übernommen
3. Problem wird gelöst
4. Supporter klickt "Ticket schließen"
5. Modal fragt nach Grund
6. Transcript wird erstellt & hochgeladen
7. User erhält DM mit Link
8. Channel/Thread wird gelöscht
```

### Join-Modus Workflow
```
1. User erstellt Ticket
2. Join-Embed erscheint in Join-Channel
3. Supporter sieht das Embed
4. Supporter klickt "Ticket joinen"
5. Supporter wird zum Ticket hinzugefügt
6. Embed zeigt beigetretene Supporter
```

---

## 🛠️ Troubleshooting

### Bot reagiert nicht auf Commands
```
✓ Bot hat Administrator-Rechte?
✓ Commands mit /tree.sync() synchronisiert?
✓ Bot ist online?
```

### Buttons funktionieren nicht
```
✓ Views in ticket_events.py geladen?
✓ custom_id korrekt gesetzt?
✓ timeout=None für Persistence?
```

### GitHub Upload fehlschlägt (404)
```
✓ Repository existiert und ist public?
✓ Token hat "repo" Scope?
✓ GitHub Pages aktiviert?
✓ Branch name korrekt? (main/master)
```

### Threads werden nicht gefunden
```
✓ Thread im richtigen Channel?
✓ is_ticket_channel() unterstützt Threads?
✓ Thread nicht archiviert?
```

### Weitere Hilfe benötigt
```
✓ Kontaktiere RandomAuto

```

---

## 📝 Best Practices

### Ticket-Typen
```
✓ Klare, beschreibende Namen (Support, Bug, Bewerbung)
✓ Passende Emojis für Buttons
✓ Spezifische Rollen pro Typ
```

### Modal-Felder
```
✓ Max 5 Felder (Discord Limit)
✓ Klare Labels ohne Fachbegriffe
✓ "paragraph" für längere Texte
✓ "required" nur wenn wirklich nötig
```

### Berechtigungen
```
✓ Separate Rollen für verschiedene Ticket-Typen
✓ Claim-Rollen nur für aktive Supporter
✓ Admin-Befehle nur für Admins
```

---

## 📚 Weiterführende Links

- [Discord.py Dokumentation](https://discordpy.readthedocs.io/)
- [Discord Developer Portal](https://discord.com/developers/applications)
- [GitHub Pages Docs](https://docs.github.com/pages)

---

## 🤝 Support

Bei Fragen oder Problemen:
- Überprüfe die Logs in der Console
- Checke die Troubleshooting-Sektion
- Stelle sicher dass alle Dependencies installiert sind

---

## 📜 Lizenz

Dieses Projekt ist Open Source und kann frei verwendet werden.

---

## 🎉 Credits

Erdacht und entwickelt von RandomAuto

Alle Rechte vorbehalten

© Randoms Coding Spot 2025

**Features:**
- Persistent Views & Buttons
- GitHub Transcript Integration
- Thread & Channel Support
- Join-Button System
- Vollständige Anpassbarkeit

---
