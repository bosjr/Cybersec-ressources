Oui. Pour présenter cela de façon professionnelle en 15 minutes, l’étudiant peut s’appuyer sur une vraie méthode d’analyse de risques suivie d’une méthode de choix des mesures de sécurité.

Le plus classique est :

* identification des actifs
* identification des menaces
* identification des vulnérabilités
* évaluation des impacts
* estimation de la vraisemblance
* calcul / qualification du niveau de risque
* traitement du risque
* choix des mesures de sécurité

Le choix des mesures n’est donc pas “au hasard”, il découle du traitement du risque.

---

# Méthodes reconnues

## 1. EBIOS Risk Manager (très utilisé en France)

Méthode recommandée par l’ANSSI.

Elle permet :

* d’identifier les événements redoutés
* d’analyser les sources de risque
* de prioriser les risques
* de définir les mesures de sécurité adaptées

Très apprécié dans les soutenances.

---

## 2. ISO/IEC 27005

Norme internationale orientée management du risque SSI.

Elle structure :

* identification
* analyse
* évaluation
* traitement des risques

Puis :

* éviter
* réduire
* transférer
* accepter le risque

---

## 3. Méthode simplifiée pédagogique

Souvent utilisée en Bachelor :

### Exemple simple

| Risque        | Impact | Probabilité |   Niveau | Mesure                              |
| ------------- | -----: | ----------: | -------: | ----------------------------------- |
| Ransomware    |      5 |           4 | Critique | sauvegardes + MFA + sensibilisation |
| Phishing      |      4 |           5 |    Élevé | filtrage mail + formation           |
| Panne serveur |      4 |           3 |    Moyen | PRA + supervision                   |

Ici la mesure est choisie selon :

* le niveau de criticité
* le coût
* la faisabilité
* la conformité réglementaire
* le retour sur investissement sécurité

---

# Il existe bien une méthode pour choisir les mesures

On parle de :

# stratégie de traitement du risque

Les choix possibles sont :

## Réduire

Exemple :

* pare-feu
* MFA
* EDR
* segmentation réseau

## Éviter

Exemple :

* suppression d’un service exposé

## Transférer

Exemple :

* cyberassurance
* externalisation

## Accepter

Exemple :

* risque faible avec coût de protection trop élevé

---

# Trame de présentation orale (15 min)

L’étudiant peut dire :

### 1. Contexte

présentation de l’entreprise / SI

### 2. Identification des actifs critiques

serveurs, AD, sauvegardes, données RH, ERP…

### 3. Analyse des menaces

phishing, ransomware, erreur humaine, panne, intrusion…

### 4. Évaluation des risques

matrice impact × probabilité

### 5. Priorisation

classement des risques majeurs

### 6. Choix des mesures

justification technique, financière et organisationnelle

### 7. Plan d’action

court / moyen / long terme

---

Pour une soutenance, je conseille fortement de dire :

“J’ai utilisé une approche inspirée d’EBIOS Risk Manager”

# Étapes exactes de la méthode EBIOS Risk Manager

La méthode ANSSI EBIOS RM repose sur **5 ateliers**.

L’objectif est de passer d’une vision métier des risques à la définition des mesures de sécurité adaptées.

---

# Atelier 1 — Cadrage et socle de sécurité

Objectif :

définir le périmètre de l’étude et les éléments essentiels.

On identifie :

* le contexte de l’organisation
* le périmètre étudié
* les valeurs métier (actifs essentiels)
* les événements redoutés
* le socle de sécurité existant
* les référentiels applicables (RGPD, ISO 27001, etc.)

Exemple :

* données clients
* Active Directory
* ERP
* messagerie
* sauvegardes

---

# Atelier 2 — Sources de risque

Objectif :

identifier les acteurs susceptibles de porter atteinte au système.

On analyse :

* les sources de risque internes
* les sources de risque externes
* leurs motivations
* leurs ressources
* leurs capacités d’attaque

Exemple :

* cybercriminels
* employé malveillant
* prestataire négligent
* concurrent
* hacktiviste

---

# Atelier 3 — Scénarios stratégiques

Objectif :

comprendre comment une source de risque pourrait atteindre l’objectif visé.

On étudie :

* les chemins d’attaque indirects
* les dépendances
* les partenaires
* les prestataires
* la supply chain

Exemple :

attaquer un prestataire VPN pour atteindre l’entreprise.

---

# Atelier 4 — Scénarios opérationnels

Objectif :

décrire techniquement l’attaque.

On précise :

* les vulnérabilités exploitables
* les actions techniques possibles
* les étapes de compromission
* les impacts potentiels

Exemple :

phishing → vol de credentials → accès VPN → mouvement latéral → ransomware

---

# Atelier 5 — Traitement du risque

Objectif :

définir les mesures de sécurité pertinentes.

On décide :

* réduire le risque
* éviter le risque
* transférer le risque
* accepter le risque

Puis on choisit :

* mesures techniques
* mesures organisationnelles
* mesures humaines
* mesures contractuelles

Exemple :

* MFA
* PRA/PCA
* EDR
* segmentation réseau
* sauvegardes immuables
* sensibilisation utilisateurs

---

# Résumé ultra simple

## EBIOS RM = 5 questions

### 1. Qu’est-ce qui est important ?

→ Atelier 1

### 2. Qui peut nous attaquer ?

→ Atelier 2

### 3. Par où peuvent-ils passer ?

→ Atelier 3

### 4. Comment attaquent-ils concrètement ?

→ Atelier 4

### 5. Que met-on en place ?

→ Atelier 5

---

# En soutenance (version courte)

L’étudiant peut dire :

> J’ai utilisé une démarche inspirée d’EBIOS Risk Manager :
> cadrage, identification des sources de risque,
> scénarios stratégiques et opérationnels,
> puis traitement des risques avec choix des mesures de sécurité.

(terminologie EBIOS RM) :

de cadrer le périmètre de l’étude et réaliser la cartographie des valeurs métiers et des biens supports
d’identifier les événements redoutés (ER)
d’analyser les sources de risque (SR) et les objectifs visés (OV) associés
de construire les scénarios stratégiques et opérationnels d’attaque
d’évaluer la vraisemblance et l’impact des risques
de prioriser les risques selon leur criticité
de définir la stratégie de traitement des risques
de choisir les mesures de sécurité techniques, organisationnelles et humaines adaptées

