# Guide de démarrage rapide - TravauxBash

## 🚀 Démarrage immédiat

### 1. Ouvrir l'application
- Ouvrez `index.html` dans votre navigateur web
- L'application fonctionne entièrement côté client, aucun serveur n'est nécessaire

### 2. Configurer votre clé API
1. Obtenez une clé API GitHub Models sur https://github.com/marketplace/models
2. Sélectionnez le modèle `gpt-4o-audio-preview`
3. Copiez votre clé API
4. Collez-la dans le champ "Clé API GitHub Models (OpenAI)"
5. La clé sera sauvegardée automatiquement dans votre navigateur

### 3. Enregistrer vos travaux
1. Cliquez sur **"Démarrer l'enregistrement"**
2. Autorisez l'accès au microphone si demandé
3. Décrivez les travaux à effectuer naturellement en français

**Exemple:**
> "Dans la cuisine, au niveau du mur nord, il faut réparer la prise électrique. Appeler un électricien. Dans la salle de bain, au plafond, il y a une fuite d'eau à corriger. Besoin d'un plombier."

### 4. Utiliser les contrôles
- **⏸️ Pause**: Met l'enregistrement en pause (le chronomètre s'arrête)
- **▶️ Reprendre**: Continue l'enregistrement (le chronomètre reprend)
- **⏹️ Terminer et analyser**: Arrête l'enregistrement et lance l'analyse IA

### 5. Consulter les résultats
Après l'analyse, un tableau s'affiche avec:
- **Pièce**: Zone ou pièce concernée
- **Emplacement**: Position précise
- **Objet**: Élément à réparer/modifier
- **Artisan**: Type d'artisan requis

## 📱 Utilisation mobile

L'application est optimisée pour mobile et inclut:
- **Wake Lock**: L'écran ne se mettra pas en veille pendant l'utilisation
- **Design responsive**: S'adapte à toutes les tailles d'écran
- **Touches larges**: Boutons faciles à utiliser avec le doigt

## 🔧 Fonctionnalités avancées

### Formats audio supportés
L'application détecte automatiquement les formats audio disponibles:
- audio/webm (préféré)
- audio/mp4
- audio/ogg

### Stockage local
Vos préférences sont sauvegardées:
- Clé API (stockée localement, jamais partagée)
- Derniers paramètres utilisés

## ⚠️ Prérequis

### Navigateurs compatibles
- Chrome/Edge 84+
- Firefox 89+
- Safari 15+
- Opera 70+

### APIs requises
- MediaRecorder API
- getUserMedia API
- Wake Lock API (optionnel mais recommandé)
- Fetch API
- LocalStorage

**Note**: Vous pouvez vérifier la compatibilité en ouvrant `test.html`

## 🔒 Sécurité et confidentialité

### Données privées
- Tous les enregistrements sont traités localement
- Seul l'audio final est envoyé à GitHub Models pour l'analyse
- Aucune donnée n'est conservée sur des serveurs externes

### Clé API
- Stockée uniquement dans votre navigateur (localStorage)
- Jamais transmise à des tiers
- Utilisée uniquement pour les appels à GitHub Models

## 🐛 Dépannage

### Le microphone ne fonctionne pas
- Vérifiez que vous avez autorisé l'accès au microphone
- Assurez-vous qu'aucune autre application n'utilise le micro
- Testez dans un autre navigateur

### L'analyse ne fonctionne pas
- Vérifiez que votre clé API est correcte
- Assurez-vous d'avoir accès au modèle `gpt-4o-audio-preview`
- Vérifiez votre connexion internet

### Le wake lock ne fonctionne pas
- Cette fonctionnalité n'est pas disponible sur tous les appareils
- Elle est optionnelle et n'affecte pas les autres fonctionnalités

## 📝 Exemples d'utilisation

### Inspection d'appartement
> "Salon, mur ouest, fissure au plafond, plâtrier. Chambre principale, fenêtre côté rue, vitre cassée, vitrier. Cuisine, sous l'évier, fuite du robinet, plombier."

### Suivi de chantier
> "Étage 2, appartement A, peinture porte d'entrée écaillée, peintre. Couloir commun, néon grillé au plafond, électricien. Parking niveau -1, place 23, sol fissuré, maçon."

### Finitions
> "Bureau, angle nord-est, plinthe décollée, menuisier. Salle de réunion, tableau blanc, fixation cassée, maintenance. Hall d'entrée, carrelage tâché, nettoyage professionnel."

## 📞 Support

Pour toute question ou problème:
1. Vérifiez ce guide
2. Consultez `test.html` pour tester les APIs
3. Ouvrez une issue sur le dépôt GitHub

## 🎯 Bonnes pratiques

1. **Parlez clairement**: Articulez bien pour une meilleure reconnaissance
2. **Structurez vos phrases**: Mentionnez pièce, emplacement, problème, artisan
3. **Enregistrements courts**: Préférez plusieurs courts enregistrements qu'un très long
4. **Vérifiez les résultats**: Relisez toujours le tableau généré
5. **Sauvegardez régulièrement**: Copiez les résultats importants ailleurs

## 🔄 Mises à jour

L'application est un fichier HTML autonome. Pour mettre à jour:
1. Téléchargez la dernière version de `index.html`
2. Remplacez votre ancien fichier
3. Vos paramètres (clé API) seront conservés
