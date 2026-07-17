# JOMA IMPACT ACADEMY — Prototype front-end

## Ce que contient ce livrable

- `index.html` — site étudiant : inscription/connexion, sélection de domaine, cours, QCM, JOMA Coins, paiement Moov Money, certificat PDF.
- `admin.html` — espace administrateur : valider les demandes de certificat, voir la liste des étudiants.
- `style.css` — design system complet (couleurs, composants, responsive).
- `app.js` — toute la logique (comptes, progression, quiz, coins, certificat).

Domaine **Blockchain** entièrement construit (11 leçons + QCM de 6 questions) pour valider le concept de bout en bout, comme convenu. Les 7 autres domaines apparaissent en façade avec la mention « Bientôt » : leur contenu (leçons + QCM) reste à rédiger, et suivra exactement la même structure de données dans `app.js` (objet `DOMAINS`).

## ⚠️ Limite importante : ceci est un prototype, pas un site prêt pour la production

Tout est stocké dans le `localStorage` du navigateur : pas de vraie base de données, pas de serveur.

Concrètement, ça veut dire :
- Un étudiant inscrit sur son téléphone n'existera pas s'il se connecte depuis un ordinateur.
- Les mots de passe ne sont pas chiffrés — ne jamais utiliser cette version en ligne telle quelle.
- Le code d'accès admin (`JOMA-ADMIN-2026`, dans `admin.html`) est visible par quiconque regarde le code source. Il ne protège rien de sérieux.
- L'admin ne voit que les étudiants inscrits **dans le même navigateur** que lui.

C'est volontaire à ce stade : l'objectif était de valider rapidement le parcours complet (inscription → cours → QCM → paiement → validation → certificat) avant d'investir dans un vrai backend. Pour mettre le site en ligne réellement, il faut la suite qu'on avait évoquée : un backend (Firebase ou Node.js + base de données) qui remplace `loadUsers()` / `saveUsers()` / `updateUser()` dans `app.js` par de vrais appels API, avec des mots de passe hashés et un accès admin protégé par un vrai compte.

## Publicités

Les scripts publicitaires ne sont pas encore réactivés (voir commentaire en haut de `index.html`). Les emplacements sont prêts (`.ad-zone`) : bannière haute, bannière basse, encart 300×250 dans les cours. Remets tes scripts réels au moment où tu voudras les activer.

## Comment tester

Ouvre `index.html` dans un navigateur (double-clic suffit, pas besoin de serveur). Crée un compte, termine les 11 leçons de Blockchain, réussis le QCM (70% requis), envoie une capture d'écran factice pour la demande de certificat, puis ouvre `admin.html` (code : `JOMA-ADMIN-2026`) dans le même navigateur pour valider la demande — le certificat devient alors téléchargeable côté étudiant.

## Prochaines étapes proposées

1. Choisir le backend (Firebase ou Node.js + base de données) pour remplacer le stockage local.
2. Rédiger le contenu des 7 domaines restants sur le modèle de Blockchain.
3. Remplacer le code d'accès admin par un vrai compte protégé côté serveur.
4. Réactiver les scripts publicitaires.
5. Étendre la traduction EN au contenu des cours (actuellement seule l'interface est bilingue).
