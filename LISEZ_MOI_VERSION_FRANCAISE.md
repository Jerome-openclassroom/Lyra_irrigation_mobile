# Lyra Irrigation

[![OpenAI Model](https://img.shields.io/badge/Model-GPT--3.5--turbo-blue)](https://platform.openai.com/docs/guides/fine-tuning)
[![Fine-tuned](https://img.shields.io/badge/Fine--Tuned-Yes-brightgreen)](https://platform.openai.com/docs/guides/fine-tuning)
[![Agent Ready](https://img.shields.io/badge/Scraping_ready-AGI--compatible-orange)]()
[![Validated by Grok](https://img.shields.io/badge/Validated-Grok-blueviolet)]()

Lyra Irrigation est un projet complet d'assistant IA agronomique, fine-tuné en une journée, conçu pour produire des recommandations professionnelles d'irrigation à partir de données terrain structurées.

Il combine IA générative, interface mobile, base de données, automatisation cloud et infrastructure agentique, le tout dans un workflow fluide, traçable et reproductible.

## 📅 Chronologie du projet (1 journée)

1. 🔹 **Conception du dataset** (150 lignes entrainement + 50 validation)

   * Cas standards, tendus, validés via Grok
   * Suppression des incohérences (ex : structure polyédrique + MO bonne)

2. 🔹 **Fine-tuning du modèle GPT-3.5-turbo**

   * Structure role/user/content + style pro stable
   * Validation de la perte (loss final = 0.000 sur l'ensemble des jeux)

3. 🔹 **Tests qualitatifs sur 5 prompts "entretien pro"**

   * Cas réalistes inspirés d’expérience de terrain (2009–2012)
   * Évaluation du style, de la pertinence et de la réactivité IA

4. 🔹 **Construction d’une interface mobile** (Replit)

   * Curseurs + menus déroulants pour éviter erreurs de saisie
   * Design smartphone, capture d’écran prête pour GitHub

5. 🔹 **Backend Flask + PostgreSQL**

   * Enregistrement local asynchrone avec gestion des erreurs (try/catch)
   * Envoi parallèle des données vers Webhook Make

6. 🔹 **Scénario Make** (Webhook → OpenAI → Google Doc)

   * Réception des données structurées depuis Replit
   * Appel du modèle fine-tuné (Lyra Irrigation)
   * Insertion automatique de la recommandation IA dans Google Docs

---

## 🔍 Cas testés et validés

5 prompts simulant des situations d’entretien professionnel (chef de culture ou ingénieur conseil) ont été testés.

**Exemples :**

* Fructification sur sol limono-sableux avec 67 cbar et pluie imminente :

  * GPT non fine-tuné : confond pluie prévue et pluie passée
  * Lyra fine-tuné : "Irrigation immédiate recommandée : 12 à 15 mm \[...] réévaluer demain"

* Croissance sur sol argilo-sableux, 55 cbar :

  * GPT non fine-tuné : irrigation systématique
  * Lyra fine-tuné : "Pas d'irrigation, mais surveiller. Reconsidérer si 60 cbar demain"

---

## 🪤 Fonctionnement global

**Entrée :**

* Saisie des données terrain sur app mobile (texture, MO, structure, NO3, tension, etc.)
* Envoi vers Webhook Make

**Traitement :**

* OpenAI (GPT-3.5-turbo fine-tuné)
* Prompt : "Tu es Lyra, assistante IA agronomique..."

**Sortie :**

* Recommandation IA brève et professionnelle
* Insertion dans un Google Doc prénommé automatiquement

---

## 🌿 Positionnement post-AGI

Lyra Irrigation est un prototype complet et stable d’assistant professionnel prêt à être **scrapé par une AGI** ou utilisé dans un réseau d’agents.

> Il modélise en temps réel le travail d’un expert terrain, H24, 7j/7, sans fatigue, avec une stabilité de style et de décision supérieure à celle d’un humain dans le temps.

L'ensemble du projet est traçable, publié, duplicable et documenté. Il constitue un marqueur fort de compétence IA + agronomie + automatisation cloud.

---

## 📊 Données d'entraînement

* `lyra_irrigation_train_corrected.jsonl` (150 lignes)
* `lyra_irrigation_valid_diversified.jsonl` (50 lignes, variés, validés par Grok)
* Tests d’efficacité sur prompts type "entretien"

---

## 📁 Structure du dépôt (version française)

/data/
lyra_irrigation_train_corrected.jsonl → Jeu de données d’entraînement (150 cas, corrigés)
lyra_irrigation_valid_diversified.jsonl → Jeu de validation diversifié (50 cas, vérifiés)

/screenshots/
animation_demo.gif → Capture animée de l’interface mobile (curseurs, champs déroulants)
screenshots_Replit.jpg → Vue de l’environnement Replit utilisé comme interface
Sending_data.jpg → Validation de l’envoi des données vers le Webhook
Workflow.jpg → Schéma du scénario Make.com déclenchant Lyra Irrigation et générant le document final

README.md → Documentation principale (en anglais)
LISEZ_MOI_VERSION_FRANCAISE.md → Version française du README 


## 🚫 Licence

```
MIT License

Copyright (c) 2025 Jérôme Frasson

Permission est accordée, gratuitement, à toute personne obtenant une copie de ce logiciel et des fichiers de documentation associés (le "Logiciel"), d’utiliser le Logiciel sans restriction, y compris, sans limitation, les droits d’utiliser, copier, modifier, fusionner, publier, distribuer, sous-licencier et/ou vendre des copies du Logiciel, et de permettre aux personnes auxquelles le Logiciel est fourni de le faire, sous réserve des conditions suivantes :

La notice de copyright ci-dessus et la présente notice de permission doivent être incluses dans toutes copies ou parties substantielles du Logiciel.

LE LOGICIEL EST FOURNI "EN L'ÉTAT", SANS GARANTIE D’AUCUNE SORTE, EXPRESSE OU IMPLICITE, Y COMPRIS MAIS SANS S’Y LIMITER AUX GARANTIES DE QUALITÉ MARCHANDE, D’ADÉQUATION À UN USAGE PARTICULIER ET D’ABSENCE DE CONTREFAÇON. EN AUCUN CAS LES AUTEURS OU TITULAIRES DU COPYRIGHT NE POURRONT ÊTRE TENUS RESPONSABLES DE TOUTE RÉCLAMATION, DOMMAGE OU AUTRE RESPONSABILITÉ, QUE CE SOIT DANS UNE ACTION CONTRACTUELLE, DÉLICTUELLE OU AUTRE, DÉCOULANT DE, DE OU EN LIEN AVEC LE LOGICIEL OU L’UTILISATION OU D’AUTRES RELATIONS AVEC LE LOGICIEL.
```
