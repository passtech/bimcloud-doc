### La branche Settings/BCF contient la visionneuse mapbox qui est intégré à la visualisation complète d'un projet

#### deux dossiers ont été ajouter dans cette branche: le dossier ifcjs-mapbox et le dossier project-list-main.



Le dossier ifcjs-mapbox, qui se trouve dans la librairie ifcjs, possède le composant ifcjs-mapbox-viewer qui permet d'afficher une scène mapbox.



Le dossier project-list-main se trouve dans la partie bimcloud-frontend du dossier apps et contient le composant bimcloud-project-list-main, bimcloud-project-list-viewer et bimcloud-project-list-table.

Bimcloud-project-list-main permet de charger et de transmettre les informations essentielles pour le bon fonctionnement des deux autres composants.

Bimcloud-project-list-viewer affiche une scène mapbox. le point centrâle de la scène peut être déplacer lorsque l'on clique sur l'un des noms des fichiers enregistré dans le tableau en dessous.
Le fichier choisis possèdera un fond bleu lorsque la scène est basé sur son addresse.

Bimcloud-project-list-table montre toutes les informations des fichiers du projet avec, en plus, la possibilité de changer l'addresse, de télécharger le fichier et de supprimer le fichier.