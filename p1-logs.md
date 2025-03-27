---
description: Ús de logs en Python
---

# 🗒️ P1 - Logs

## 🎯 Objectius

* Entendre la diferència entre `print()` i `logging`.
* Escriure missatges d’informació, advertència i error.
* Guardar els logs en un fitxer.

## 📄 Introducció

Els tècnics en sistemes sovint han de registrar què fa un programa. Els _logs_ serveixen per analitzar el funcionament i trobar errors quan alguna cosa no va bé. Python ofereix un mòdul anomenat `logging` per a això.

## 🧪 Exemple bàsic

```python
import logging

# Configura el sistema de log
logging.basicConfig(
    filename='log_programa.log',
    level=logging.DEBUG,
    format='%(asctime)s - %(levelname)s - %(message)s'
)

logging.debug("Missatge per a depuració.")
logging.info("El programa ha començat.")
logging.warning("Això és una advertència.")
logging.error("S'ha produït un error.")
```

## 🔧 Exercicis proposats

1. **Configura un script que escriga diferents tipus de missatges de log** (`debug`, `info`, `warning`, `error`) i comprova que es guarden en un fitxer.
2. **Fes un petit programa que demane a l’usuari un número. Si no introdueix un número vàlid, registra un error en el log.**
3. **Canvia la configuració del `logging` perquè els missatges es vegen també per pantalla.**
4. **Crea un log rotatiu** (pista: `logging.handlers.RotatingFileHandler`).
5. **Extra:** Canvia el format del log perquè tinga només hora i missatge.

## ✅ Avaluació

* Correcta implementació dels nivells de log.
* Format clar i entenedor.
* Missatges ben triats segons el context.
* Logs guardats correctament en un fitxer.
