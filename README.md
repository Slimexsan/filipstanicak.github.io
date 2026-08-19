# Lebenslauf-Website — Filip Stanicak

Statische Seite ohne Build und ohne Framework. Zwei Dinge müssen zusammen hochgeladen werden:

```
index.html
assets/
  portrait.jpg      700 × 933 px, 71 KB — Porträt im Hero (2x-Auflösung)
  portrait@1x.jpg   350 × 467 px, 22 KB — dasselbe Bild für normale Displays
  avatar.jpg        180 × 180 px,  7 KB — runder Zuschnitt für Navigation und Mobilansicht
```

Einzige externe Abhängigkeit sind die Google Fonts (siehe „Datenschutz" unten).

## Inhalt

Mischung aus beiden Lebensläufen:

| Aus der **Beratungsversion** | Aus der **Industrieversion** |
|---|---|
| Rolle „Senior Consultant", Beratungssprache | „rund sieben Jahre Automotive-Erfahrung" (statt fünf) |
| Fachliche Führung, Partnerstrategie, Pre-Sales | Steuergeräte-/E2E-Tiefe, Kalibrierungsumfeld |
| KPI-Systeme, Vorgehensmodelle, AI-Enablement | „Prozesse dort aufbauen, wo keine bestanden" |
| Vollständige Projektübersicht (10 Projekte) | Bosch-Details, Bachelorarbeit-Bezug |

Sektionen: Profil · Schwerpunkte · Werdegang · Projekte (filterbar) · Kompetenzen · Kontakt.
Dark Mode richtet sich automatisch nach der Systemeinstellung. Ein Druck-Stylesheet ist hinterlegt:
Wer die Seite über Strg+P ausgibt, bekommt ein sauberes Dokument ohne Navigation und Filter — ein
eigener Button dafür ist bewusst nicht vorhanden.

## Bild

Quelle: `1000039253.jpg` aus dem Karriere-Ordner (2147 × 2862 px, 3,2 MB). Für das Web verkleinert
und auf Qualität 84–86 komprimiert, damit die Seite schnell lädt.

Darstellung:

- **Desktop** — Porträt im 3:4-Format rechts neben dem Text, abgerundet, mit einem dünnen,
  versetzten Rahmen in der Akzentfarbe dahinter. Darunter eine kurze Bildunterschrift.
- **Schmale Viewports (unter 820 px)** — statt der Porträtkarte ein rundes Avatar (104 px) über dem
  Namen. Umgeschaltet wird per `<picture>`-Element, es lädt also nur die jeweils passende Datei.
- **Navigation** — dasselbe Avatar in 29 px neben dem Namen.

Ein anderes Foto einsetzen: die drei Dateien in `assets/` mit gleichen Namen und Seitenverhältnissen
ersetzen. Das Porträt muss 3:4 sein (Hochformat), das Avatar quadratisch mit etwas Luft über dem Kopf.

## URLs und Kontaktdaten

`canonical` und `og:image` stehen auf `https://filipstanicak.github.io/`. Bei einem Wechsel auf eine
eigene Domain beide Zeilen (10 und 16) anpassen — das `og:image` muss absolut bleiben, sonst zeigen
LinkedIn und WhatsApp beim Teilen kein Vorschaubild.

**Bewusst nicht enthalten:** Telefonnummer und Anschrift. Die Seite nennt nur E-Mail, LinkedIn und
„Region Stuttgart". HTML-Kommentare sind kein Versteck — sie werden mitausgeliefert und stehen im
Quelltext. Kontaktdaten, die nicht öffentlich sein sollen, gehören deshalb gar nicht erst in die
Datei, sondern in die Bewerbungsunterlagen.

## Hosting-Optionen (alle kostenlos, ohne Werbung, mit seriöser URL)

### Empfehlung 1 — GitHub Pages (kürzeste kostenlose URL)

Ergibt `https://filipstanicak.github.io` — ohne Pfad-Anhängsel, sofern das Repository **exakt**
`<benutzername>.github.io` heißt.

1. GitHub-Account anlegen, Benutzername z. B. `filipstanicak`.
2. Neues **öffentliches** Repository mit dem Namen `filipstanicak.github.io`.
3. `index.html` **und den Ordner `assets`** per „Add file → Upload files" hochladen (beide
   gleichzeitig in das Upload-Feld ziehen, damit die Ordnerstruktur erhalten bleibt), committen.
4. Settings → Pages → Source: `Deploy from a branch`, Branch `main`, Ordner `/ (root)`.
5. Nach ~1 Minute ist die Seite live.

Vorteile: dauerhaft kostenlos, HTTPS inklusive, Versionshistorie. Nachteil: Der GitHub-Account ist
öffentlich sichtbar.

### Empfehlung 2 — Cloudflare Pages (ohne Git, reines Drag & Drop)

Ergibt `https://filip-stanicak.pages.dev`.

1. Kostenloses Cloudflare-Konto erstellen.
2. Workers & Pages → Create → Pages → **Upload assets**.
3. Projektname `filip-stanicak` eingeben, den **gesamten Projektordner** (mit `index.html` und
   `assets`) hineinziehen, „Deploy".

Vorteile: kein Git nötig, sehr schnelles CDN, unbegrenzter Traffic. Der Projektname bestimmt die
Subdomain — also einen sauberen Namen wählen.

### Alternativen

| Anbieter | URL-Form | Anmerkung |
|---|---|---|
| Netlify | `filip-stanicak.netlify.app` | Drag & Drop, sehr komfortabel |
| Vercel | `filip-stanicak.vercel.app` | eher entwicklerorientiert |
| GitLab Pages | `filipstanicak.gitlab.io` | Alternative zu GitHub |

**Nicht empfehlen:** kostenlose Massenhoster wie 000webhost, Freehostia oder ähnliche — die blenden
Werbung ein, hängen Werbe-Subdomains an und sind für eine Bewerbungsseite ungeeignet.

### Für Bewerbungen die beste Variante: eigene Domain

`filipstanicak.de` kostet rund 5–15 € pro Jahr (z. B. bei netcup, INWX oder Namecheap) und lässt
sich bei **allen** oben genannten Hosts kostenlos einbinden — das Hosting bleibt also gratis, nur die
Domain kostet. Im Lebenslauf und in Anschreiben wirkt `filipstanicak.de` deutlich souveräner als eine
`.github.io`-Adresse.

Einbindung: beim Host die Domain als „Custom Domain" hinterlegen, dann beim Domain-Anbieter die
angezeigten DNS-Einträge (CNAME bzw. A-Records) setzen. HTTPS-Zertifikat wird automatisch erzeugt.

## Datenschutz-Hinweis (relevant, wenn die Seite öffentlich ist)

Die Seite lädt zwei Schriftarten von Google Fonts. Dabei wird die IP-Adresse der Besucher an Google
übertragen — nach deutscher Rechtsprechung (LG München I, 3 O 17493/20) ohne Einwilligung
problematisch. Zwei einfache Lösungen:

- **Schriften lokal einbinden**: Dateien herunterladen, neben `index.html` legen und per `@font-face`
  referenzieren.
- **Auf Systemschriften umstellen**: Der `<link>` zu Google Fonts wird entfernt, die Fallback-Stacks
  (`-apple-system`, `Segoe UI`, `Georgia`) greifen automatisch. Optisch minimal schlichter, dafür
  keine externen Requests.

Ein **Impressum** ist für eine rein private, nicht geschäftsmäßige Lebenslaufseite in der Regel nicht
erforderlich; sobald sie der Kundengewinnung dient (z. B. Freelancing), wird es Pflicht. Im Zweifel
eine kurze Impressum-Sektion ergänzen.
