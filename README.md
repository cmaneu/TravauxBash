# TravauxBash 🏗️

Application web pour les directeurs de chantier permettant d'organiser les travaux de construction via enregistrement vocal et analyse IA.

## 📄 Pages disponibles

- **`index.html`** : Page principale avec analyse de travaux structurée (extraction de pièce, emplacement, objet, artisan)
- **`transcribe.html`** : Page de transcription multiple avec enregistrement walkie-talkie et stockage des transcriptions

## 🎯 Fonctionnalités

### Page principale (index.html)

- **🔒 Verrouillage d'écran** : Empêche l'appareil de se mettre en veille pendant l'utilisation
- **🎤 Enregistrement vocal** : Système complet avec démarrage, pause, reprise et arrêt
- **🤖 Analyse IA** : Utilise OpenAI via GitHub Models pour analyser les enregistrements
- **📊 Organisation automatique** : Génère un tableau structuré avec :
  - Pièce
  - Emplacement
  - Objet
  - Artisan requis
- **🇫🇷 Interface en français** : Entièrement localisée

### Page de transcription (transcribe.html)

- **🎙️ Enregistrement walkie-talkie** : Maintenez le bouton enfoncé pour enregistrer, relâchez pour transcrire automatiquement
- **🗣️ Transcription IA** : Utilise Azure OpenAI gpt-4o-transcribe pour transcrire en français
- **💾 Stockage persistant** : Sauvegarde automatique des transcriptions dans IndexedDB
- **📝 Liste de transcriptions** : Affiche toutes les transcriptions avec horodatage
- **🗑️ Suppression facile** : Bouton de suppression pour chaque transcription
- **🇫🇷 Interface en français** : Entièrement localisée

## 🚀 Utilisation

### Page principale (index.html)

#### Méthode 1 : Utilisation standard
1. Ouvrez `index.html` dans un navigateur web moderne
2. Configurez le point de terminaison API (par défaut : GitHub Models)
3. Entrez votre clé API GitHub Models (OpenAI)
4. Cliquez sur "Démarrer l'enregistrement" pour commencer
5. Décrivez les travaux à effectuer vocalement
6. Utilisez "Pause" pour interrompre temporairement
7. Cliquez sur "Terminer et analyser" pour obtenir le tableau organisé

#### Méthode 2 : Configuration via URL (paramètres de requête)
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

### Page de transcription (transcribe.html)

1. Ouvrez `transcribe.html` dans un navigateur web moderne
2. Configurez votre endpoint Azure OpenAI (ex: `https://votre-instance.openai.azure.com`)
3. Entrez votre clé API Azure OpenAI
4. Ajustez la température si nécessaire (par défaut : 0.82)
5. **Maintenez le bouton microphone enfoncé** pour commencer l'enregistrement
6. Parlez en français
7. **Relâchez le bouton** pour arrêter l'enregistrement et lancer la transcription automatique
8. La transcription s'ajoute automatiquement à la liste
9. Les transcriptions sont sauvegardées et rechargées à chaque visite

## 🔑 Configuration

### Page principale (index.html)

#### Point de terminaison API

L'application permet de configurer le point de terminaison OpenAI :
- **Par défaut** : `https://models.inference.ai.azure.com/chat/completions` (GitHub Models)
- **Personnalisable** : Vous pouvez utiliser n'importe quel endpoint compatible OpenAI
- **Via URL** : Passez le paramètre `endpoint` dans l'URL

#### Clé API

Vous aurez besoin d'une clé API GitHub Models pour utiliser la fonctionnalité d'analyse IA :

1. Visitez [GitHub Models](https://github.com/marketplace/models)
2. Obtenez une clé API pour le modèle `gpt-4o-audio-preview`
3. **Option A** : Entrez la clé dans le champ prévu dans l'application
4. **Option B** : Passez la clé via le paramètre `key` dans l'URL

Les paramètres (endpoint et clé API) sont sauvegardés localement dans votre navigateur pour une utilisation ultérieure.

### Page de transcription (transcribe.html)

#### Point de terminaison API Azure OpenAI

Vous devez configurer l'URL de base de votre instance Azure OpenAI :
- **Format** : `https://votre-instance.openai.azure.com`
- Le chemin complet `/openai/deployments/gpt-4o-transcribe/audio/transcriptions` est automatiquement ajouté

#### Clé API Azure OpenAI

1. Obtenez une clé API depuis votre instance Azure OpenAI
2. Assurez-vous d'avoir déployé le modèle `gpt-4o-transcribe`
3. Entrez la clé dans le champ prévu

#### Température

- Contrôle la créativité de la transcription (0-1)
- Par défaut : 0.82
- Valeurs plus basses = plus déterministe
- Valeurs plus hautes = plus créative

Les paramètres sont sauvegardés localement dans votre navigateur.

## 📱 Compatibilité

- Navigateurs modernes avec support de :
  - MediaRecorder API
  - getUserMedia API
  - Wake Lock API (index.html)
  - Fetch API
  - IndexedDB (transcribe.html)
  - Streaming Response (transcribe.html)
- Optimisé pour mobile (responsive design)
- Support tactile pour le mode walkie-talkie (transcribe.html)

## 🛠️ Technologies utilisées

- HTML5
- **CSS3 personnalisé** - Styles modernes et responsives intégrés (gradient, animations, design mobile-first)
- JavaScript (vanilla)
- MediaRecorder API
- Wake Lock API (index.html)
- OpenAI GPT-4o Audio Preview via endpoint configurable (index.html - GitHub Models par défaut)
- Azure OpenAI gpt-4o-transcribe API (transcribe.html)
- IndexedDB pour stockage persistant (transcribe.html)

## 📝 Exemple d'utilisation

### Page principale (index.html)

Parlez simplement des travaux à effectuer :

> "Dans la cuisine, au niveau du mur nord, il faut réparer la prise électrique. Appeler un électricien. Dans la salle de bain, au plafond, il y a une fuite d'eau à corriger. Besoin d'un plombier."

L'application générera automatiquement un tableau organisé :

| Pièce | Emplacement | Objet | Artisan |
|-------|-------------|-------|---------|
| Cuisine | Mur nord | Prise électrique | Électricien |
| Salle de bain | Plafond | Fuite d'eau | Plombier |

### Page de transcription (transcribe.html)

1. Maintenez le bouton microphone enfoncé
2. Dites : "Déplacer la cloison de la salle de bain pour retoucher la ferme"
3. Relâchez le bouton
4. La transcription apparaît automatiquement dans la liste : "Déplacer la cloison de la salle de bain pour retoucher la ferme"
5. Répétez pour ajouter d'autres transcriptions

## 🔐 Sécurité

- La clé API et l'endpoint sont stockés uniquement dans le localStorage de votre navigateur
- Aucune donnée n'est envoyée à des serveurs tiers (sauf l'API configurée)
- L'enregistrement audio est traité localement avant l'envoi
- Aucune dépendance externe - CSS intégré dans le fichier HTML