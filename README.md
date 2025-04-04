# Protocol
Release Series: “The Architect's Protocol”


# GhostNode – Week 1 Release  
**Passive Backdoor Node by The Architect**

> “The quietest signals carry the loudest truths.”

GhostNode is a stealth-layer NFC-based system designed to silently trigger, relay, or intercept local activity from nearby devices. This is Week 1 of an ongoing multi-stage release from *The Architect*, designed to give power back to the people—one line of code at a time.

---

## File Structure

### `ghostnode_core.py`  
Main execution logic for NFC-based detection and relay.
- Monitors for proximity-based signals
- Triggers pre-configured scripts upon device detection
- Logs unique device identifiers locally (hashed)

---

### `payload_handler.py`  
Handles actions GhostNode can take on detection.
- Executes payloads (e.g., local logging, beaconing, silent script)
- Supports customizable module import structure
- Obfuscated by default to prevent static detection

---

### `suicide_switch.py`  
Failsafe kill-switch module.
- Destroys runtime traces upon detection of tampering
- Scrubs memory and temporary storage
- Optional NFC-triggered self-destruct sequence

---

### `config.json`  
User-defined node behavior.
- `trigger_radius`: Acceptable detection distance
- `action`: Define behavior on signal (log, relay, execute)
- `obfuscation`: Toggle signature mutation
- `self_destruct`: Optional auto-wipe config

---

### `nfc_daemon.service`  
Linux systemd service file for persistent background operation.
- Installs GhostNode as a stealth daemon
- Auto-starts on boot
- Hidden logs + memory residency

---

### `README.md`  
This document.  
A tactical layout of everything released in Week 1.

---

## Usage (Advanced Operators Only)

1. Install required dependencies:
```bash
pip install nfcpy cryptography
