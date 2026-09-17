# RunnerRino – Projekt-Roadmap & To-Do-Liste

**Projekt:** RunnerRino  
**Beschreibung:** Ein körpergesteuertes Ausweichspiel (Endless Runner im Stil von Subway Surfers / Temple Run), steuerbar über Pose-Recognition via Kamera.

---

## Status Quo
- [x] Spielkonzept und Grundidee definiert
- [x] Posen (Links, Rechts, Ducken, Springen, Neutral) in Teachable Machine trainiert
- [x] Git-Repository aufgesetzt

---

## To-Do-Liste

### Meilenstein 1: Model-Export & Kamera-Integration
- [ ] **Teachable Machine Model exportieren**
  - Modell als TensorFlow.js / Web-Modell exportieren
  - Model-Dateien (`model.json`, `metadata.json`, `weights.bin`) im Git-Repository ablegen
- [ ] **Kamera-Stream & Modell laden**
  - Web-App / Skript erstellen, das den Webcam-Feed abgreift
  - TensorFlow.js und Teachable Machine Library einbinden
  - Modell beim Start der Anwendung laden
- [ ] **Echtzeit-Klassifizierung testen**
  - Posen-Erkennung live im Browser/Konsole überprüfen
  - Erkennungsrate und Genauigkeit der Posen evaluieren
- [ ] **Schwellenwert (Confidence Threshold) festlegen**
  - Mindestwahrscheinlichkeit (z. B. 80–85 %) definieren, ab wann eine Pose als Aktion akzeptiert wird

---

### Meilenstein 2: Input-Verarbeitung & Event-Handling
- [ ] **Cooldown / Debounce-Logik implementieren**
  - Zeitfenster/Sperre nach einer Aktion einbauen, um Mehrfacherkennungen zu vermeiden
- [ ] **Neutral-State / Rückstellung steuern**
  - Logik festlegen, dass der Spieler vor der nächsten Aktion wieder in die neutrale Position zurückkehren muss
- [ ] **Event-Bridge (Posen → Steuerung) erstellen**
  - Erkannte Posen in virtuelle Tastatur-Events (z. B. `ArrowLeft`, `ArrowRight`, `ArrowUp`, `ArrowDown`) oder Event-Emitter umwandeln
- [ ] **Fallback-Steuerung einbauen**
  - Tastatur-Steuerung zu Test- und Debugging-Zwecken aktivieren

---

### Meilenstein 3: Game Framework & Logik
- [ ] **Spielfeld & Spielfigur erstellen**
  - Grundgerüst für ein 3-Spuren-System (Links, Mitte, Rechts) aufbauen (z. B. mit Three.js, PhaserJS oder HTML5 Canvas)
- [ ] **Charakter-Mechanik programmieren**
  - Spurwechsel (Links / Rechts)
  - Sprung-Mechanik (Kurzzeitiges Ausweichen nach oben)
  - Duck-Mechanik (Kurzzeitiges Verkleinern/Abducken)
- [ ] **Hindernis-Generator (Spawner)**
  - Zufallserzeugung von Hindernissen auf den 3 Spuren
  - Unterschiedliche Hindernistypen (hohe Hindernisse → Ducken, tiefe Hindernisse → Springen, voll besetzte Spuren)
- [ ] **Kollisionsabfrage (Hitboxen)**
  - Präzise Abfrage, ob Figur und Hindernis kollidieren

---

### Meilenstein 4: Integration, Polish & Spielschleife
- [ ] **Posenerkennung mit Spiellogik verknüpfen**
  - Posen-Input direkt mit den Bewegungen des Spielcharakters verbinden
- [ ] **Latenz-Optimierung**
  - Verzögerung zwischen Bewegung vor der Kamera und Reaktion im Spiel minimieren
- [ ] **Game-Loop & UI**
  - Startbildschirm / Anweisungen zur Kalibrierung
  - Punktestand-Anzeige (Score / Distanz)
  - Game-Over-Bildschirm mit Restart-Option
- [ ] **Feinschliff & Testing**
  - Beleuchtungsverhältnisse und Kameraabstände testen
  - Bugfixing und Feintuning der Bewegungssensitivität
