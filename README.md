# Philips Hue Tap Dial – Home Assistant ZHA Blueprint

Blueprint für den **Philips Hue Tap Dial Switch (RDM002)** über Zigbee Home Automation (ZHA).

## Funktionen

- Vier Tasten, jeweils frei mit Leuchten/Schaltern und optional einer Szene belegbar.
- Erneutes Drücken einer Taste schaltet deren konfigurierte Geräte/Leuchten aus.
- Das Drehrad dimmt alle aktuell eingeschalteten Leuchten, die in den vier Tasten-Zuordnungen hinterlegt sind.
- Dimm-Schritt zwischen 1 und 50 Prozent einstellbar.

## Installation

1. Öffne die [Blueprint-YAML-Datei](blueprints/automation/philips_hue_tap_dial_zha.yaml).
2. Klicke auf **Raw** und kopiere die URL.
3. Importiere sie in Home Assistant über:

`https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://raw.githubusercontent.com/bp8st6jwqc-ux/Home-Assistant-Philips-Hue-Tap-Dial/main/blueprints/automation/philips_hue_tap_dial_zha.yaml`

4. Wähle deinen Hue Tap Dial und konfiguriere die vier Tasten.

## Szenen und Ausschalten

Eine Szene kann selbst nicht ausgeschaltet werden. Wenn du eine Taste mit einer Szene belegst, wähle deshalb zusätzlich unter **Geräte / Leuchten** die Leuchten aus, die diese Szene steuert. Beim nächsten Tastendruck werden diese Leuchten ausgeschaltet.

## Hinweise

- Der Hue Tap Dial muss bereits über **ZHA** in Home Assistant eingebunden sein.
- Die Drehradsteuerung berücksichtigt nur Leuchten (`light.*`), keine Schalter.
- Die Blueprint wertet ZHA-Ereignisse des ausgewählten Geräts aus.
- Nach dem Import die Automation speichern und testen. Die tatsächlichen ZHA-Ereignisse können in **Entwicklerwerkzeuge → Ereignisse** mit dem Ereignistyp `zha_event` geprüft werden.