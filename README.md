# MAX Explorer — dossier de publication

Carte des trajets TGV INOUI / Intercités à 0 € pour les abonnés MAX Jeune et MAX Senior.
L'application tient dans **un seul fichier** : `index.html`. Il n'y a rien à installer ni de serveur à maintenir.

| Fichier      | Rôle |
|--------------|------|
| `index.html` | L'application complète (carte, données de fond et bibliothèque Leaflet incluses). |
| `_headers`   | En-têtes de sécurité pour Netlify et Cloudflare Pages (ignoré par GitHub Pages, sans effet négatif). |

- **Données** : « SNCF Open Data — Disponibilité à 30 jours de places MAX JEUNE et MAX SENIOR », licence ODbL (mention déjà affichée dans la page, rubrique « À propos et licences »). Relisez les conditions : <https://data.sncf.com/pages/licence>.
- **Instantané** : les données sont mises à jour une fois par jour, en début de matinée. La page invite à confirmer sur SNCF Connect avant de réserver.
- **Indépendance** : le service n'est pas affilié à la SNCF (mention incluse). N'utilisez ni logo ni charte graphique de la SNCF.
- **Correspondances** : le jeu de données ne contient que des trajets directs. Les options « 1 changement » (jaune) et « 2+ changements » (rouge) sont calculées par la page en enchaînant des directs à 0 € (battement de 15 min à 3 h, 2 changements maximum, 7 jours maximum). Chaque tronçon se réserve séparément ; la page le précise.
- **Aucun serveur, aucune collecte** : chaque visiteur interroge directement l'API SNCF depuis son navigateur. La page ne dépose pas de cookie ; elle mémorise seulement les derniers choix (gares, dates) dans le navigateur du visiteur.
- **Si SNCF modifie son jeu de données** : la page affiche un message d'erreur avec les champs reçus, ce qui permet de savoir quoi corriger dans `index.html`.
- **Sécurité** : la page contient une politique de sécurité (CSP) qui n'autorise les requêtes réseau que vers `ressources.data.sncf.com`. Si vous ajoutez un jour une autre source de données, il faudra l'ajouter à la ligne `Content-Security-Policy` en haut de `index.html`.

## Crédits et licences des composants

- Données de disponibilité : SNCF Open Data (ODbL).
- Contours des départements et régions : IGN Admin Express, version simplifiée publiée sur GitHub par « gregoiredavid » (dépôt `france-geojson`) — Licence Ouverte Etalab.
- Contours des pays voisins : Natural Earth (domaine public), via le paquet `world-atlas`.
- Cartographie interactive : [Leaflet](https://leafletjs.com) 1.9.4, licence BSD-2 (l'avis de copyright est conservé dans le fichier).
