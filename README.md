# RetroRadio Reverse 📻⚡

> Open-source reverse engineering, preservation, and modern tooling for vintage transceivers, legacy DOS/Win32 Radio Service Software (RSS), and EEPROM memory programming.

## Project Scope

Many legendary commercial and amateur radios from Yaesu/Vertex, Motorola, Kenwood, and Icom rely on obsolete 16-bit MS-DOS or Windows 3.1/95/XP software to program channel frequencies, CTCSS/DCS tones, and RF parameters.

**RetroRadio Reverse** aims to:
1. **Reverse engineer** legacy binary protocols and EEPROM memory maps.
2. Provide **`retrorig`**, a modern cross-platform Python CLI/library to read, edit, and flash radios directly via standard USB-UART cables on modern Linux/macOS/Windows systems without DOSBox or old PCs.
3. Document packet structures, checksum algorithms, and pinouts for historical preservation.

## Supported Radios

| Manufacturer | Model | Original Software | Protocol Status | Tooling |
| :--- | :--- | :--- | :--- | :--- |
| **Yaesu / Vertex** | FTL-2011 / FTL-7011 / FTL-1011 | CE5 (DOS, 1993) | ✅ Checksum & Data Map Verified | `retrorig` CLI (In progress) |

---

## The `retrorig` CLI

```bash
# Clone memory dump from radio
retrorig read ftl2011 /dev/ttyUSB0 -o backup.bin

# Export channel list to editable CSV/JSON
retrorig dump backup.bin -o channels.csv

# Write modified channels back to radio
retrorig write ftl2011 /dev/ttyUSB0 -i channels.csv
```

## License
MIT
