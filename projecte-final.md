---
description: Eina de diagnòstic de xarxa amb Python
---

# 🧑‍🔬 Projecte Final

## 🎯 Objectius

* Aplicar tot el que hem après durant el curs.
* Crear una eina funcional i útil per a un tècnic de sistemes.
* Aprendre a treballar amb biblioteques com `ipaddress`, `psutil` i `logging`.

## 📄 Descripció

El teu repte és construir una **eina de diagnòstic bàsic per a la xarxa i el sistema** que:

1. Mostre informació del sistema (CPU, RAM, disc, sistema operatiu, usuari...).
2. Accepte una subxarxa com `192.168.1.0/24` i faça ping a totes les IPs vàlides.
3. Guarde els resultats (disponibilitat de cada IP, hora, ús de CPU, etc.) en un fitxer.
4. Mostre els errors o advertències amb el sistema de **logging**.
5. (Opcional) Genere un fitxer HTML o JSON amb un petit informe.

## 🛠️ Eines recomanades

* `logging` per a registrar missatges.
* `psutil` per a la informació del sistema.
* `ipaddress` per a calcular el rang d’IPs d’una subxarxa.
* `subprocess` per a fer els pings.
* `datetime` per a afegir hora/data als registres.

## 🔧 Exemple de càlcul d’IPs amb la màscara CIDR

```python
import ipaddress

def obtenir_ips(cidr):
    xarxa = ipaddress.ip_network(cidr, strict=False)
    return [str(ip) for ip in xarxa.hosts()]

# Exemple:
print(obtenir_ips("192.168.1.0/26"))  # Dona 62 IPs
```

## 🧱 Estructura mínima recomanada

* `main.py`: script principal
* `sistema.py`: funcions per a llegir informació del sistema
* `scanner.py`: funcions per fer ping i processar IPs
* `logs/`: carpeta on es guarden els fitxers `.log`
* `resultats/`: carpeta amb els resultats del ping en `.txt` o `.json`

## ✅ Entrega

* Tot el codi en un repositori o carpeta zip.
* Fitxer `README.md` amb:
  * Com executar el programa
  * Explicació breu del que fa
  * Estructura del projecte

## 🏁 Avaluació

| Criteri                                    | Punts |
| ------------------------------------------ | ----- |
| Estructura del projecte clara              | 1     |
| Codi funcional i ben comentat              | 2     |
| Logs generats correctament                 | 1     |
| Informació del sistema mostrada            | 1     |
| Ping sobre subxarxa correctament processat | 2     |
| Resultats guardats en fitxer               | 2     |
| Extra: informe HTML/JSON ben formatat      | +1    |
