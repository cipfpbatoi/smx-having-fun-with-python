---
description: Informació de l'ordinador amb Python
---

# 🖥️ P2 - Hardware

## 🎯 Objectius

* Aprendre a usar mòduls per obtenir informació del sistema.
* Mostrar la informació del processador, memòria i sistema operatiu.
* Escriure eixos resultats en un fitxer.

## 📄 Introducció

Els tècnics han de saber com consultar la informació de l’ordinador. Amb Python, es pot fer fàcilment usant mòduls com `platform` o `psutil`.

## 🔍 Mòduls que farem servir

* `platform` – Mostra informació del sistema operatiu.
* `psutil` – Mostra informació de la CPU i la memòria.
* `getpass` – (extra) Saber quin usuari està usant el sistema.

> ⚠️ Per a usar `psutil`, potser hauràs d’instal·lar-lo amb `pip install psutil`.

## 🧪 Exemple bàsic

```python
import platform
import psutil
import getpass

print("Nom d'usuari:", getpass.getuser())
print("Sistema operatiu:", platform.system(), platform.release())
print("Arquitectura:", platform.architecture()[0])
print("Processador:", platform.processor())

print("CPU utilització (%):", psutil.cpu_percent(interval=1))
print("Memòria RAM total:", round(psutil.virtual_memory().total / (1024**3), 2), "GB")
```

## 🔧 Exercicis proposats

1. **Executa el codi d’exemple i interpreta el resultat.**
2. **Modifica el programa perquè guarde tota la informació en un fitxer de text.**
3. **Mostra també l’espai disponible al disc dur.**
4. **(Opcional)** Afegeix al final del fitxer la data i l’hora en què s’ha executat el programa (`from datetime import datetime`).

## 💡 Pista per a guardar en un fitxer

```python
CopiaModificwith open("info_sistema.txt", "w") as f:
    f.write("Sistema operatiu: " + platform.system() + "\n")
    # escriu més línies...
```

## ✅ Avaluació

* Codi comentat i comprensible.
* Informació rellevant mostrada i guardada.
* Fitxer generat correctament amb l’extensió `.txt`.
