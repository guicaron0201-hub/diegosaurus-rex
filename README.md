# 🦕 Le Parc de Diego

App web d'escape game créée pour les 1 an de Diego — thème dinosaures / parc d'attractions.
~30 invités, 5-6 équipes, jeu en extérieur (jardin, pétanque, forêt).

Ce dépôt est prévu pour être développé avec **Claude Code**. Ce README sert de brief à donner
directement à Claude Code pour démarrer le projet. Voir aussi `GAME_DESIGN.md` pour le contenu
du jeu (énigmes, codes, scénario).

---

## 1. Contexte & objectif

Le système de sécurité du parc a lâché. Chaque équipe doit parcourir 3 enclos (zones du terrain),
résoudre une énigme par enclos pour obtenir un code, puis débloquer le "labo génétique" final
qui annonce que le parc est sécurisé — signal pour passer au gâteau.

Un adulte (le papa) joue le rôle du T-Rex en costume dans la zone forêt, en interaction physique
avec les équipes (voir `GAME_DESIGN.md`).

## 2. Fonctionnalités attendues (MVP)

- [ ] Page de connexion par équipe (nom d'équipe + code d'équipe)
- [ ] Carte du parc avec 3 enclos, statut sécurisé / non sécurisé, compteur de progression
- [ ] Écran énigme par enclos : indice affiché + champ de saisie de code + validation
- [ ] Écran final "système réactivé" quand les 3 enclos sont faits
- [ ] Progression persistante et partagée par équipe (si plusieurs membres d'une équipe
      ouvrent l'app sur leur téléphone, ils voient la même progression)
- [ ] Responsive mobile en priorité (le jeu se joue sur téléphone, en extérieur)

## 3. Fonctionnalités "si le temps le permet"

- [ ] Scan de QR code (un QR code par enclos, redirige directement vers l'énigme correspondante)
- [ ] Galerie photo : upload d'une photo "preuve de mission" à chaque enclos réussi, visible
      par tous en fin de partie
- [ ] Classement / timer live entre équipes
- [ ] Écran admin simple pour suivre la progression de toutes les équipes en direct

## 4. Stack technique suggérée

- Frontend simple : HTML/CSS/JS, ou React si Claude Code préfère (pas de besoin de complexité)
- Stockage : pas de backend dédié nécessaire dans un premier temps — privilégier une solution
  simple (ex. stockage clé-valeur type Supabase, ou équivalent léger) pour la progression
  partagée par équipe et les photos
- Déploiement : Netlify, Vercel ou GitHub Pages (statique + petite base de données si besoin)
- Pas d'authentification complexe : un simple code d'équipe suffit

## 5. Contenu du jeu

Voir `GAME_DESIGN.md` pour :
- Le scénario complet
- Les 3 enclos, leurs indices et leurs codes
- Le rôle du T-Rex (papa en costume)
- Le matériel à imprimer

## 6. Prototype existant

Un premier prototype visuel (HTML statique, un seul fichier) existe déjà et peut servir de base
de design : palette jungle/ambre, typographie façon caisse d'expédition/parc naturel, écrans
login → carte → énigme → final. À réutiliser ou retravailler librement.

## 7. Plan de développement suggéré pour Claude Code

1. Reprendre ou reconstruire les 4 écrans (login, carte, énigme, final) à partir du style du
   prototype
2. Brancher un vrai code d'équipe différent par équipe (actuellement un seul code de démo)
3. Ajouter le stockage partagé de la progression par équipe
4. Ajouter la génération/lecture de QR codes par enclos
5. Ajouter l'upload photo si le temps le permet
6. Tester sur mobile en conditions réelles (extérieur, plein soleil, réseau faible)
7. Déployer et générer les supports à imprimer (QR codes, fiches de mission)

## 8. Contraintes pratiques

- Jeu en extérieur, prévoir un mode qui fonctionne même avec un réseau mobile faible
- Testé pour être utilisable par des enfants et des adultes (langage simple dans les énigmes)
- Doit rester utilisable même si une équipe se retrouve sans réseau un instant (éviter de tout
  perdre en cas de coupure)
