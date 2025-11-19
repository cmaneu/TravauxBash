# TravauxBash 🏗️

Application web pour les directeurs de chantier permettant d'organiser les travaux de construction via enregistrement vocal et analyse IA.

## 🎯 Fonctionnalités

- **🔒 Verrouillage d'écran** : Empêche l'appareil de se mettre en veille pendant l'utilisation
- **🎤 Enregistrement vocal** : Système complet avec démarrage, pause, reprise et arrêt
- **🤖 Analyse IA** : Utilise OpenAI via GitHub Models pour analyser les enregistrements
- **📊 Organisation automatique** : Génère un tableau structuré avec :
  - Pièce
  - Emplacement
  - Objet
  - Artisan requis
- **🇫🇷 Interface en français** : Entièrement localisée

## 🚀 Utilisation

1. Ouvrez `index.html` dans un navigateur web moderne
2. Configurez le point de terminaison API (par défaut : GitHub Models)
3. Entrez votre clé API GitHub Models (OpenAI)
4. Cliquez sur "Démarrer l'enregistrement" pour commencer
5. Décrivez les travaux à effectuer vocalement
6. Utilisez "Pause" pour interrompre temporairement
7. Cliquez sur "Terminer et analyser" pour obtenir le tableau organisé

## 🔑 Configuration

### Point de terminaison API

L'application permet de configurer le point de terminaison OpenAI :
- **Par défaut** : `https://models.inference.ai.azure.com/chat/completions` (GitHub Models)
- **Personnalisable** : Vous pouvez utiliser n'importe quel endpoint compatible OpenAI

### Clé API

Vous aurez besoin d'une clé API GitHub Models pour utiliser la fonctionnalité d'analyse IA :

1. Visitez [GitHub Models](https://github.com/marketplace/models)
2. Obtenez une clé API pour le modèle `gpt-4o-audio-preview`
3. Entrez la clé dans le champ prévu dans l'application

Les paramètres (endpoint et clé API) sont sauvegardés localement dans votre navigateur pour une utilisation ultérieure.

## 📱 Compatibilité

- Navigateurs modernes avec support de :
  - MediaRecorder API
  - getUserMedia API
  - Wake Lock API
  - Fetch API
- Optimisé pour mobile (responsive design)

## 🛠️ Technologies utilisées

- HTML5
- **Tailwind CSS** (via CDN) - Framework CSS moderne et responsive
- JavaScript (vanilla)
- MediaRecorder API
- Wake Lock API
- OpenAI GPT-4o Audio Preview via endpoint configurable (GitHub Models par défaut)

## 📝 Exemple d'utilisation

Parlez simplement des travaux à effectuer :

> "Dans la cuisine, au niveau du mur nord, il faut réparer la prise électrique. Appeler un électricien. Dans la salle de bain, au plafond, il y a une fuite d'eau à corriger. Besoin d'un plombier."

L'application générera automatiquement un tableau organisé :

| Pièce | Emplacement | Objet | Artisan |
|-------|-------------|-------|---------|
| Cuisine | Mur nord | Prise électrique | Électricien |
| Salle de bain | Plafond | Fuite d'eau | Plombier |

## 🔐 Sécurité

- La clé API et l'endpoint sont stockés uniquement dans le localStorage de votre navigateur
- Aucune donnée n'est envoyée à des serveurs tiers (sauf l'API configurée)
- L'enregistrement audio est traité localement avant l'envoi
- Tailwind CSS chargé via CDN officiel (https://cdn.tailwindcss.com)