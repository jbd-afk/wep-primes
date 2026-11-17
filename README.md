# 🏀 WEP Primes

PWA de suivi des primes de parrainage bancaire pour financer le week-end WEP (~200 €/personne).

## Mise en ligne (GitHub Pages, gratuit)

1. Dans le dépôt : **Settings → Pages → Source : Deploy from a branch → main / (root)**
2. Une minute plus tard, l'appli est en ligne sur `https://jbd-afk.github.io/wep-primes/`

## Installation par WEPien

- **Android / Chrome** : menu ⋮ → « Ajouter à l'écran d'accueil »
- **iPhone / Safari** : Partager → « Sur l'écran d'accueil »

## Fonctionnement

- **Mes démarches** : checklist des étapes (éligibilité, lien de parrainage, KYC, dépôt, conditions, prime, cagnotte) avec les délais max usuels. Sauvegarde locale automatique (localStorage).
- **Le groupe** : qui ouvre dans quelle banque, qui parraine qui, totaux de la cagnotte, boutons de sync ⬆ Partager / ⬇ Récupérer.
- **Les offres** : primes filleul/parrain des banques (montants de novembre 2026, à revérifier) + règles d'or.
- **Réglages** : date du WEP (compte à rebours), coût par personne, mode cagnotte, URL de sync groupe.

## Sync groupe (état partagé)

Renseigner dans Réglages l'URL d'une ressource JSON unique acceptant GET et PUT (une ligne de table Supabase avec sa clé anon, ou un bin JSONBin). « Partager » envoie l'état du groupe, « Récupérer » le télécharge sur un autre téléphone. Chaque téléphone garde une copie locale hors ligne.

## Intégration future dans la PWA WEP

L'app expose `WepPrimes.mount(el)` pour être rendue dans n'importe quel conteneur, `WepPrimes.get()/set(k,v)` pour l'état, et s'exporte en module (`module.exports`). Fichier unique, zéro dépendance.