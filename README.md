# Wahlgrafiken und Kartenprojekt

## Projektstruktur

```
testbtw/
├── backend/                 # Django Backend
│   ├── config/             # Django Projekteinstellungen
│   ├── api/                # REST API für Wahldaten
│   ├── election_data/      # App für Wahlmanagement
│   └── requirements.txt    # Python Dependencies
│
├── frontend/               # Frontend Anwendung
│   ├── src/
│   │   ├── components/    # Wiederverwendbare UI Komponenten
│   │   ├── maps/         # Kartenkomponenten (Leaflet/OpenMap GL)
│   │   ├── charts/       # Grafikkomponenten (D3.js)
│   │   └── utils/        # Hilfsfunktionen
│   └── package.json
│
└── data/                  # Datenverwaltung
    ├── schemas/           # Datenbankschemas
    └── migrations/        # Datenbankmigrations
```

## Technologie-Stack

### Backend
- Django: Web Framework
- Django REST Framework: API Entwicklung
- PostgreSQL: Datenbank für Wahlergebnisse
- Channels: Websocket für Echtzeit-Updates

### Frontend
- React: UI Framework
- D3.js: Datenvisualisierung
- Leaflet: Kartenintegration
- Chakra UI: UI Komponenten
- WebSocket: Echtzeit-Datenaktualisierung

## Features
1. Echtzeit-Wahlergebnisanzeige
2. Interaktive Wahlkarten
   - Bundesländer
   - Wahlkreise
   - Gemeinden
3. Verschiedene Grafiktypen
   - Balkendiagramme
   - Tortendiagramme
   - Zeitreihen
4. Einbettbare Widgets (iframes)
   - Einzelne Grafiken
   - Karten
   - Kombinierte Dashboards

## Datenmodell

### Wahlergebnisse
- Wahlebene (Bund/Land/Kreis/Gemeinde)
- Partei
- Stimmenanzahl
- Prozentuale Verteilung
- Timestamp der letzten Aktualisierung

### Geografische Daten
- Geometrien für verschiedene Verwaltungsebenen
- Verknüpfung mit Wahlergebnissen

## API-Endpunkte

### REST API
- `/api/v1/results/` - Aktuelle Wahlergebnisse
- `/api/v1/regions/` - Geografische Informationen
- `/api/v1/parties/` - Parteien und deren Metadaten

### WebSocket
- `ws://domain/ws/results/` - Echtzeit-Updates

## Deployment
- Backend: Django auf Docker
- Frontend: Netlify
- Datenbank: Managed PostgreSQL
