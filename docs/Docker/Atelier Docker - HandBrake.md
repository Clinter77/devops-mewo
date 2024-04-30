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
Une fois la vidéo trouvée, il faut la monter dans un volume.
Création du volume : docker volume create nom_du_volume
Copier la vidéo dans le volume Docker : cp /chemin/vers/la/nom_video.mp4 $(docker volume inspect --format '{{ .Mountpoint }}' my_volume)
Ensuite monter le volume dans le Container Docker : docker run -it --rm -v nom_du_volume:/chemin_du_container ubuntu /bin/bash

## Quelles commandes permettent d'inspecter les détails et les logs d'un conteneur actif?
Pour inspecter docker inspect id_container : docker inspect caa571803fd1
Pour vérifier ses logs docker logs id_container : docker logs caa571803fd1

## Comment arrêter, redémarrer, et finalement supprimer un conteneur et une image?
Pour le démarrer docker start id_container : docker start caa571803fd1
Pour le stopper docker pause id_container : docker pause caa571803fd1
Et pour supprimer : docker rm 
