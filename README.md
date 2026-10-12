# Les Dossiers Interdits

Jeu d'enquête coopératif pour deux écrans : Inspecteur Nicolas Gollum et Capitaine Prêtresse Suzanne. Affaires procédurales, 90 minutes, chat synchronisé, preuves propres à chaque rôle, interrogatoires, accusation et score.

## Installation (Mac, GitHub et Firebase)

1. Créer un projet sur https://console.firebase.google.com/ et y enregistrer une **application Web**.
2. Copier la configuration affichée dans `firebase-config.js` (apiKey, authDomain, projectId, appId).
3. Dans **Authentication > Sign-in method**, activer **Anonyme**.
4. Dans **Firestore Database**, créer une base puis copier le contenu de `firestore.rules` dans l'onglet **Règles**, et publier.
5. Importer tous les fichiers à la racine d'un dépôt GitHub. Dans **Settings > Pages**, sélectionner **Deploy from a branch**, branche `main`, dossier `/ (root)` et enregistrer. L'URL publique apparaîtra après déploiement. Ou utiliser Firebase Hosting.
6. Sur le premier écran, créer une partie. Sur le second, ouvrir le même lien, saisir le code à 6 caractères et choisir l'autre personnage. Le créateur lance la partie.

## Notes importantes

- Cette version est un **prototype jouable** et non un service de production sécurisé. Firestore autorise la lecture des salles à toute personne authentifiée anonymement : les secrets de l'affaire peuvent être consultés par un utilisateur technique. Pour un jeu compétitif ou public, déplacer la solution dans un document privé/Cloud Functions, sécuriser les règles et valider chaque action côté serveur.
- Le moteur produit des combinaisons cohérentes, mais utilise des trames narratives fixes. Il ne produit pas encore de dialogues libres par IA, d'illustrations dynamiques, de voix, ni de véritable puzzle complexe. L'ambiance et la difficulté sont enregistrées mais ne modifient pas encore la logique des affaires.
- Le générateur produit des variations d'affaires, avec 5 types de crimes, 5 lieux, 6 suspects, 8 indices et 1 coupable par partie.
- La partie se termine au bout de 90 minutes ou dès l'accusation. Le chrono repose sur l'horloge du navigateur, et n'est pas résistant aux manipulations.
- Pour un usage personnel, partager uniquement le lien et le code avec le partenaire. Ne jamais ajouter de clés de service privées Firebase au dépôt.
