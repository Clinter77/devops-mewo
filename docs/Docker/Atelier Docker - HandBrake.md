# Atelier Docker - HandBrake

## Quelle commande utiliseriez-vous pour télécharger l'image Docker de HandBrake?
Tout d'abord : docker search handbrake pour lister les images disponibles avec ce terme
puis : docker pull jlesage/handbrake

## Comment lanceriez-vous un conteneur HandBrake pour traiter une vidéo située sur votre machine hôte?
Lister ses Containers et voir leurs id de Containers, leurs images, leurs status : docker ps -a
Ouvrir et lancer le Container : docker start 8faa11aba477 et docker run 8faa11aba477
Vérifier les Containers qui tournent actuellement : docker ps -q
Rentrer dans le Container pour voir son contenu : docker exec -it 8faa11aba477 /bin/bash
Si la vidéo n'est pas présente dans ce Container, sortir du Container actuel avec exit puis chercher dans un autre (commandes ls et cd .. utiles pour naviguer dans l'arborescence)

## Quelles commandes permettent d'inspecter les détails et les logs d'un conteneur actif?

## Comment arrêter, redémarrer, et finalement supprimer un conteneur et une image?

