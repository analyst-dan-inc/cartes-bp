# Carte du budget participatif de Saint-Denis

Ce dépôt contient les deux pages de la carte actuelle, leur fichier de données et cette documentation. Les fichiers inutilisés ont été retirés de la version courante. Ils restent disponibles dans les historiques Git des deux dépôts réunis.

## Fichiers

- `index.html` : page de présentation et carte.
- `map.html` : carte seule, destinée à l’intégration.
- `carte-projets-bp.json` : fichier actuellement chargé par les deux cartes (99 projets au moment du regroupement).

## Données et mises à jour

Selon l’auteur, les données des projets proviennent de l’API publique Cap Collectif de bp.saintdenis.re. Les pages lisent une copie JSON : elles n’interrogent pas directement cette API. Aucun script d’extraction ou de synchronisation n’est fourni dans les dépôts récupérés.

Les champs du fichier actif sont : id, title, bodyText, url, category, edition_bp, formatted_address, lat, lng, statut et quartier. La provenance publique ne remplace pas une vérification des textes, adresses et versions historiques avant toute décision de diffusion.

## Utilisation et hébergement

Les fichiers HTML peuvent être servis par un hébergement statique. Pour préserver le fonctionnement des intégrations existantes, `projectsUrl` pointe vers le fichier JSON brut de ce même dépôt, sur la branche main. Le dépôt budget-participatif-carte n’est plus requis par ces versions du code.

Pour transférer vers un hébergement de la Ville, déposer les fichiers sur cet hébergement et remplacer `projectsUrl` dans les deux pages par l’adresse retenue. Si les pages et le JSON sont servis au même emplacement, utiliser `./carte-projets-bp.json`. En cas de collage du code HTML dans un autre site, une adresse absolue appropriée reste nécessaire. Vérifier les accès entre domaines si les données sont hébergées ailleurs.

Les copies du code déjà intégrées sur un site ne se mettent pas automatiquement à jour : leur référence aux données doit également être modifiée.

## Dépendances externes

- Leaflet 1.9.4, MapLibre GL 2.4.0, connecteur MapLibre/Leaflet 0.0.20 et Turf 6, via unpkg.com.
- Fonds cartographiques OpenStreetMap et OpenFreeMap.
- Contours des quartiers via le jeu de données `les-20-quartiers-villesaintdenis` sur data.regionreunion.com.

Ce regroupement ne supprime pas ces dépendances. Le choix de les conserver ou de les héberger autrement relève de la reprise technique.

## Historique et ancien dépôt

Le dépôt budget-participatif-carte reste inchangé pour les intégrations qui utiliseraient encore ses URL. Il n’est ni supprimé ni archivé par cette opération. Le dépôt présent devient le point de regroupement pour la reprise et les prochaines modifications.
