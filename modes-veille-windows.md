
# 1. Modes de veille Windows

## Veille S3 (Sleep classique)

* RAM alimentée
* reprise rapide (1–3 sec)
* consommation faible

## Veille prolongée (Hibernate / S4)

* RAM écrite sur disque (`hiberfil.sys`)
* extinction quasi complète
* reprise plus lente

## Veille hybride

* S3 + sauvegarde sur disque
* protection en cas de coupure

## Veille moderne (Modern Standby / S0 Low Power Idle)

* utilisée sur PC récents
* réseau parfois actif
* comportement proche smartphone

---

## 2. Commandes principales `powercfg`

## 🔎 Voir les modes disponibles

```cmd id="pwr1"
powercfg /a
```

→ affiche :

* S3 dispo ou non
* hibernation activée
* modern standby

---

## ⚡ Activer / désactiver hibernation

### Activer

```cmd id="pwr2"
powercfg /hibernate on
```

### Désactiver

```cmd id="pwr3"
powercfg /hibernate off
```

👉 Supprime aussi `hiberfil.sys` si off

---

## 💤 Timeout veille

### Afficher config actuelle

```cmd id="pwr4"
powercfg /query
```

---

### Modifier délai veille (AC secteur)

```cmd id="pwr5"
powercfg /change standby-timeout-ac 30
```

### Batterie

```cmd id="pwr6"
powercfg /change standby-timeout-dc 15
```

(valeurs en minutes)

---

## 🔌 Écran

```cmd id="pwr7"
powercfg /change monitor-timeout-ac 10
```

---

## 🔋 Rapport consommation énergie

```cmd id="pwr8"
powercfg /energy
```

→ génère un rapport HTML :

* erreurs drivers
* wakeups abusifs
* consommation CPU

---

## 🧠 Analyse réveils PC

```cmd id="pwr9"
powercfg /lastwake
```

→ dernier périphérique ayant réveillé la machine

```cmd id="pwr10"
powercfg /waketimers
```

→ tâches planifiées qui réveillent le PC

---

## 📡 Qui peut réveiller le PC

```cmd id="pwr11"
powercfg /devicequery wake_armed
```

---

## 🛑 Désactiver réveil périphérique

```cmd id="pwr12"
powercfg /devicedisablewake "Nom du périphérique"
```

---

# 3. Cas utile (diagnostic veille instable)

Si problème de veille (réveil intempestif) :

1. analyser :

```cmd id="pwr13"
powercfg /lastwake
```

2. vérifier timers :

```cmd id="pwr14"
powercfg /waketimers
```

3. générer rapport :

```cmd id="pwr15"
powercfg /energy
```

---

# 4. Point important (lié à ton contexte précédent)

Les soucis de veille + réseau peuvent venir de :

* adaptateurs réseau VirtualBox
* DNS forcés
* inspection HTTPS antivirus
* wake-on-LAN activé

---

# Synthèse rapide

| Action              | Commande                 |
| ------------------- | ------------------------ |
| voir modes          | `powercfg /a`            |
| activer hibernation | `powercfg /hibernate on` |
| rapport énergie     | `powercfg /energy`       |
| dernier réveil      | `powercfg /lastwake`     |
| timers actifs       | `powercfg /waketimers`   |

---
Contenu global correct. Voici les compléments importants manquants pour une fiche plus “niveau SOC / admin système”.

---

# 🔧 Compléments essentiels `powercfg`

## 1. Identifier ce qui empêche la veille (TRÈS important)

```cmd id="pwr16"
powercfg /requests
```

➡️ Montre :

* processus bloquant la veille
* audio / vidéo / drivers
* antivirus / navigateur

---

## 2. Voir les schémas d’alimentation

```cmd id="pwr17"
powercfg /l
```

➡️ Liste les plans :

* Équilibré
* Performances élevées
* Économie d’énergie

---

## 3. Activer un plan

```cmd id="pwr18"
powercfg /s GUID
```

---

## 4. Modifier finement un paramètre (niveau avancé)

Exemple : veille disque

```cmd id="pwr19"
powercfg /change disk-timeout-ac 20
```

---

## 5. Réglages avancés par GUID (très utilisé en audit)

Afficher les paramètres :

```cmd id="pwr20"
powercfg /q
```

Modifier via sous-groupe :

```cmd id="pwr21"
powercfg /setacvalueindex SCHEME_CURRENT SUB_SLEEP STANDBYIDLE 0
```

➡️ utile pour scripts de durcissement

---

## 6. Désactiver les réveils réseau (Wake-on-LAN)

```cmd id="pwr22"
powercfg /devicedisablewake "Carte réseau"
```

Et vérifier :

```cmd id="pwr23"
powercfg /devicequery wake_from_any
```

---

# 🧠 Lecture SOC (ce qu’on cherche vraiment)

En incident ou troubleshooting veille, les 4 commandes clés sont :

* `/requests` → blocage actif
* `/lastwake` → cause du réveil
* `/waketimers` → planifications
* `/energy` → diagnostic global

---

# ⚠️ Point important dans ton contexte (VirtualBox + DNS + antivirus)

Dans ton cas, les causes probables de problèmes de veille instable sont souvent :

* drivers réseau VirtualBox actifs
* inspection HTTPS antivirus (Bitdefender)
* DNS personnalisés sur adaptateurs virtuels
* wake timers Windows Update

---

# 📌 Synthèse améliorée

| Objectif           | Commande                           |
| ------------------ | ---------------------------------- |
| blocage veille     | `powercfg /requests`               |
| dernier réveil     | `powercfg /lastwake`               |
| réveils planifiés  | `powercfg /waketimers`             |
| diagnostic global  | `powercfg /energy`                 |
| périphériques wake | `powercfg /devicequery wake_armed` |

---
