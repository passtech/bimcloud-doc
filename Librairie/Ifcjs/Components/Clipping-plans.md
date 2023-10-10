Ce composant permet à l'utilisateur d'activer la création de plan de coupe et d'afficher tous les plans de coupes existant dans le viewer.

Détermine si les plans de coupe doivent être affichés
clippingPlaneActive: boolean

Stocke les plans de coupes
planes: IfcPlane[]

Stocke les plans de coupes isolés
isolatedPlanes: IfcPlane[]

Service utilisé :
- [[Ifc Service]]


Définit si les plans de coupes doivent être affiché ou non
changeClippingStatus(): void

Définit si la création des plans de coupes est active ou non
activateCreation(): void

Supprime un plan de coupe
deleteClippingPlane(selectedPlane: IfcPlane): void

Définit si un plan de coupe est visible ou pas
unseeClippingControls(selectedPlane: IfcPlane): void

Isole un plan de coupe
isolatePlane(selectedPlane: IfcPlane): void

Détermine si le plan de coupe est isolé
checkIsolation(selectedPlane: IfcPlane): boolean

Calcul l'index du plan de coupe
calculIndex(selectedPlane: IfcPlane): number

Permet d'afficher l'indication au survol d'un bouton
mouseOver(event: Event): void