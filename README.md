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

### Méthode 1 : Utilisation standard
1. Ouvrez `index.html` dans un navigateur web moderne
2. Configurez le point de terminaison API (par défaut : GitHub Models)
3. Entrez votre clé API GitHub Models (OpenAI)
4. Cliquez sur "Démarrer l'enregistrement" pour commencer
5. Décrivez les travaux à effectuer vocalement
6. Utilisez "Pause" pour interrompre temporairement
7. Cliquez sur "Terminer et analyser" pour obtenir le tableau organisé

### Méthode 2 : Configuration via URL (paramètres de requête)
Vous pouvez pré-configurer l'application en passant la clé API et l'endpoint via l'URL :

```
index.html?key=VOTRE_CLE_API&endpoint=https://votre.endpoint.com
```

**Paramètres disponibles :**
- `key` ou `apiKey` : Votre clé API
- `endpoint` : L'URL du point de terminaison API

**Exemple :**
```
index.html?key=ghp_abc123&endpoint=https://models.inference.ai.azure.com/chat/completions
```

Les valeurs passées par URL sont automatiquement sauvegardées dans le navigateur.

## 🔑 Configuration

### Point de terminaison API

L'application permet de configurer le point de terminaison OpenAI :
- **Par défaut** : `https://models.inference.ai.azure.com/chat/completions` (GitHub Models)
- **Personnalisable** : Vous pouvez utiliser n'importe quel endpoint compatible OpenAI
- **Via URL** : Passez le paramètre `endpoint` dans l'URL

### Clé API

Vous aurez besoin d'une clé API GitHub Models pour utiliser la fonctionnalité d'analyse IA :

1. Visitez [GitHub Models](https://github.com/marketplace/models)
2. Obtenez une clé API pour le modèle `gpt-4o-audio-preview`
3. **Option A** : Entrez la clé dans le champ prévu dans l'application
4. **Option B** : Passez la clé via le paramètre `key` dans l'URL

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
- **CSS3 personnalisé** - Styles modernes et responsives intégrés (gradient, animations, design mobile-first)
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
- Aucune dépendance externe - CSS intégré dans le fichier HTML