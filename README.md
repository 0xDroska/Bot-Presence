# Bot de Présence Discord

Un bot Discord pour gérer les présences de manière efficace.
https://cdn.discordapp.com/attachments/1339130482557980694/1339130634030809118/2025-02-11_20-51-44.mkv?ex=67ad9a16&is=67ac4896&hm=de6a377ce3b790c0f7bab59687fcb30a25b8267fd1f8c5dd0c715df17f6c3aac&
## Prérequis

- [Node.js](https://nodejs.org/) (version 16.9.0 ou supérieure)
- Un serveur Discord où vous avez les permissions administrateur

## Installation

1. Clonez le dépôt :
```bash
git clone [url-du-repo]
cd presence
```

2. Installez les dépendances :
```bash
npm install
```

3. Configurez les variables d'environnement :S
   - Remplissez les variables suivantes dans le fichier `.env` :
     - `TOKEN` : Le token de votre bot Discord
     - `CLIENTID` : L'ID de votre application Discord
     - `GUILDID` : L'ID de votre serveur Discord
     - `LEADROLE` : L'ID du rôle requis pour utiliser les commandes
     - `MEMBERROLE` : L'ID du rôle requis pour les membres du groupe

## Configuration du Bot Discord

1. Créez une nouvelle application sur le [Portail Développeur Discord](https://discord.com/developers/applications)
2. Dans l'onglet "Bot", créez un bot et copiez son token
3. Activez les "Privileged Gateway Intents" suivants :
   - Server Members Intent
   - Message Content Intent
4. Dans l'onglet "OAuth2", sélectionnez les scopes :
   - `bot`
   - `applications.commands`
5. Sélectionnez les permissions requises :
   - Manage Messages
   - Send Messages
   - Read Message History
   - Add Reactions
   - View Channels

## Démarrage

1. Déployez les commandes slash (à faire une seule fois ou lors de modifications) :
```bash
node deploy-commands.js
```

2. Démarrez le bot :
```bash
node index.js
```

## Commandes Disponibles

- `/presence start` : Démarre une nouvelle présence
- `/presence stats` : Affiche les statistiques détaillées d'une présence
- `/presence remind` : Envoie un rappel pour la session active
- `/presence delete` : Supprime une session de présence

## Utilisation

1. Assurez-vous d'avoir le rôle LEADROLE configuré dans votre serveur
2. Utilisez `/presence start` pour créer une nouvelle session
3. Les membres peuvent répondre avec les boutons :
   - ✅ Présent
   - ❌ Absent
   - ⏰ En retard
4. Utilisez `/presence stats` pour voir les statistiques
5. Utilisez `/presence remind` pour envoyer un rappel aux membres n'ayant pas répondu
6. Utilisez `/presence delete` pour supprimer une session si nécessaire

## Structure du Projet

```
presence/
├── commands/          # Commandes du bot
├── events/           # Gestionnaires d'événements
├── helpers/          # Fonctions utilitaires
├── scripts/          # Scripts utilitaires
├── .env              # Variables d'environnement
├── config.js         # Configuration du bot
├── index.js          # Point d'entrée
└── deploy-commands.js # Déploiement des commandes
```

## Erreur

1. Vérifiez que toutes les variables d'environnement sont correctement configurées
2. Assurez-vous que le bot a les bonnes permissions dans votre serveur
3. Vérifiez les logs dans le dossier `logs/` pour plus de détails sur les erreurs

## Support

Pour toute question ou problème :
1. Vérifiez les logs d'erreur
2. Assurez-vous que votre configuration est correcte
3. Vérifiez que vous avez les dernières versions des dépendances
4. DM .droska. sur discord
