---
description: Ping i processament de xarxes amb Python
---

# 📠 P3 - Xaxes

## 🎯 Objectius

* Aprendre a fer un ping des de Python.
* Escriure una funció per comprovar si una IP respon.
* Processar cadenes per iterar sobre un rang d’IP.

## 🧪 Part 1: Comprovar si una IP funciona

### 🔧 Exemple bàsic amb funcions

```python
import subprocess
import platform

def comprovar_ip(ip):
    param = "-n" if platform.system().lower() == "windows" else "-c"
    command = ["ping", param, "1", ip]
    resultat = subprocess.run(command, stdout=subprocess.DEVNULL)
    return resultat.returncode == 0

# Exemple d'ús:
ip = "8.8.8.8"
if comprovar_ip(ip):
    print(f"La IP {ip} està activa.")
else:
    print(f"La IP {ip} NO respon.")
```

### xercici 1

1. Copia el codi anterior i prova amb diferents IPs (per exemple: `127.0.0.1`, `192.168.0.1`, `8.8.8.8`, etc).
2. Millora la funció perquè escriga en un fitxer els resultats (`activa` o `no respon`).
3. Fes que la funció també indique la data i hora en què s’ha fet la comprovació (`from datetime import datetime`).

***

## 🧪 Part 2: Processar una subxarxa

Ara volem que el programa accepte una IP amb CIDR com `192.168.1.0/24` i prove de fer ping a totes les IPs possibles d’eixa xarxa (del 192.168.1.1 al 192.168.1.254).

### 💡 Exemple de com fer-ho

```
python


CopiaModifica
def obtenir_ips(cidr):
    base = cidr.split('/')[0]
    parts = base.split('.')
    base_prefix = '.'.join(parts[:3])  # per a xarxes /24
    return [f"{base_prefix}.{i}" for i in range(1, 255)]  # excloem .0 i .255

# Exemple d’ús
xarxa = "192.168.1.0/24"
llista_ips = obtenir_ips(xarxa)
print(llista_ips[:5])  # Mostrem les 5 primeres
```

### ✅ Exercici 2

1. Combina la funció `comprovar_ip()` amb `obtenir_ips()` per fer un petit escàner de xarxa.
2. El teu script ha de mostrar quines IPs responen i quines no.
3. Guarda els resultats en un fitxer.
4. Extra (opcional): mostra el temps total que ha costat fer totes les proves (`import time`).

***

## ✅ Avaluació

* Codi amb funcions ben definides.
* Ús correcte de bucles i tractament de cadenes.
* Lògica clara i fitxer amb resultats generat.
* Entenen què significa una IP /24 i com es genera.
