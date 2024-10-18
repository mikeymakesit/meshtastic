# Meshtastic Device Config

Use the CLI tool for much simpler device configuration.
Connect your device to your computer so we can manage it via serial connection.

## Install Meshtastic CLI

```bash
python3 -m venv .venv
. .venv/bin/activate
pip3 install -Ur meshtastic
```

## Export Settings

Take a backup of device settings before applying, to recover if needed.

```bash
meshtastic --export-config > config.yml
```

## Apply settings

```bash
meshtastic --configure config.yml
```

The device will reboot 10-30 sec. after the settings are applied.

## Or, Manually apply specific settings

```bash
# Common settings
meshtastic --set lora.region US
meshtastic --set-owner Muggz
meshtastic --set-owner-short Mug

# T-Deck settings
meshtastic --set position.gps_enabled true
meshtastic --pos-fields ALTITUDE ALTITUDE_MSL DOP SATINVIEW SEQ_NO TIMESTAMP HEADING SPEED
```

