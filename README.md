# VAL Coaching — Ove × BaronBlood

Coaching-Wiki für Valorant. Gebaut als Single-Page-App, läuft komplett im Browser.

## 🚀 GitHub Pages Setup

1. Dieses Repo auf GitHub hochladen
2. GitHub → Settings → Pages → Source: `main` Branch, `/ (root)`
3. Fertig — die Seite ist live unter `https://DEIN-USERNAME.github.io/REPO-NAME`

---

## 📦 Wie die Daten funktionieren

### Zwei Schichten:

| Was | Wo gespeichert | Wer ändert es |
|-----|---------------|---------------|
| Skills, Sessions, Fehler-Karten | Im HTML-Code (`DEFAULT_DATA`) | **Ove** → direkt im Code editieren → auf GitHub pushen |
| Fortschritts-Badges (Rot/Gelb/Grün) | `localStorage` im Browser | **BaronBlood** → durch Klicken auf der Seite |

### Workflow für Ove (Inhalte hinzufügen):

**Option A – GitHub Web-Editor (einfachster Weg):**
1. `index.html` auf GitHub öffnen
2. Stift-Icon (Edit) klicken
3. Im Code den `DEFAULT_DATA`-Block suchen und bearbeiten
4. "Commit changes" klicken
5. BaronBlood refresht die Seite → sieht die neuen Inhalte

**Option B – Edit Mode auf der Seite:**
1. Seite öffnen → oben rechts "EDIT MODE" klicken
2. Inhalte hinzufügen/löschen wie gewünscht
3. Unten im Edit-Mode: "Als Code exportieren" (generiert den neuen DEFAULT_DATA Block)
4. In `index.html` einfügen → auf GitHub pushen

> ⚠️ **Wichtig:** Änderungen die Ove im Edit-Mode macht, sind **nur in seinem Browser** gespeichert (localStorage), bis er sie in den Code exportiert und pushed.

### Workflow für BaronBlood (Fortschritt tracken):

1. Seite öffnen (immer dieselbe URL)
2. In Skills/Fehler auf die Badges klicken: `—` → `Üben` → `Okay` → `Gut`
3. Badges werden automatisch gespeichert (bleiben auch nach Browser-Neustart)
4. Dashboard zeigt den aktuellen Stand

> ⚠️ **Wichtig:** Badges sind nur in **deinem Browser** gespeichert. Wenn du auf einem anderen Gerät öffnest, sind sie weg. Für mehrere Geräte → Browser-Sync oder Export-Funktion nutzen.

---

## 🛠️ Technisches

- Single HTML-Datei, kein Framework, kein Backend
- Funktioniert offline nach erstem Laden (außer Google Fonts)
- Daten-Persistenz: `localStorage` mit Key `val-coaching-v1`
