### La branche ifcjs-fragment est dédier à la manipulation des paquets components et open-bim


#### 7 composants et 1 service ont été créer dans cette branche


l'ifc-frag service est une version fragment de l'ifc service. Ce service contient tous les paramètres nécéssaires pour faire fonctionner la scène.
*Attention, le chargement d'un fichier dans la scène ne fonctionne pas à cause d'une erreur avec le web-ifc*


L'ifcjs-frag-viewer est identique à l'ifcjs-viewer. La seul différence étant qu'il marche avec l'ifc-frag service.


L'ifcjs-mapbox était un test avec l'api de mapbox. le composant peut-être affiché en remplaçant l'ifcjs-frag-viewer par l'ifcjs-mapbox dans le project-frag-viewer. Cependant, ce composant peut-être supprimer du au fait que la mapbox à été intégrer sans trop de problèmes dans la branche [[Settings BCF]].


Project-frag-viewer est identique à project-viewer sauf qu'il utilise les composants ifcjs-frag.
C'est la même chose pour import-frag-files-private.


Project-list-main est un composant permettant d'avoir deux vue alternatives du tableau des fichiers du projet. la première vue est le tableau normal tandis que la deuxième vue est une scène mapbox.
Ce composant à été bougé dans la branche [[Settings BCF]].