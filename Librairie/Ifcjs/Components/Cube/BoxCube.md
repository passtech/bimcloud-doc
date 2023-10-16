### Ce composant est utilisé pour générer le cube miniature en haut à droite de la scène.


###### **Table de tous les mesh qui composent le cube**
allMesh: Mesh[]


###### **Repositionne le cube en fonction du centroid**
repositionCube(centroid: Vector3): void

###### **Initialise les éléments du cube**
initItem(

    name: string,
    x0: number,
    y0: number,
    z0: number,
    x1: number,
    y1: number,
    z1: number
): void

###### **Initialise le cercle autour du cube**
initRing(): void

###### **Initialise le texte 3D positionné sur le cube**
initText3D(scene: Scene, name: string, x1: number, y1: number, z1: number): void

###### **Initialise le texte 3D positionné sur le cercle autour du cube**
initTextRing(scene: Scene, name: string, x1: number, y1: number, z1: number)

###### **Tourne le texte sur le cercle autour du cube**
rotateRing(name: string, textCube: TextGeometry)

###### **Tourne le texte sur le cube**
hasRotate(name: string, textCube: TextGeometry)

###### **Change la position de la caméra en fonction de la partie du cubeviewer que l'utilisateur a cliqué.**
switchPick(
	
	camera: Camera, 
	ifcCamera: IfcCamera, 
	controls0: 
	OrbitControls, 
	name: string,
	centroid: Vector3
)