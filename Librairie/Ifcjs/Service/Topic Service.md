### Ce service s'occupe de la gestion des topics.


###### **Définit si une projection du marqueur peut-être créer (utile pour [[Topic-form]] et [[Topic-Edit]])**
isProjected: boolean

###### **Table des topics**
localTopics: Topic[]

###### **Table des marqueurs**
markers: Array<{

    projectName: string;
    modelMesh: Mesh;
    modelLabel: THREE.Sprite;
}>

###### **Le nom de l'utilisateur**
author: string

###### **L'index du projet**
projectId: string

###### **Table des subscriptions**
subscriptions: Subscription[]

Constructeur :
- private AuthFacade
- private [[Viewer-facade]]

###### **Créer un marqueur dans la scène**
createMesh(

    intersec: THREE.Intersection,
    form: string,
    color: string,
    title: string,
    date?: Date
): Mesh | undefined

###### **Gère la rotation du marqueur selon la surface**
setMeshRotation(

    intersec: THREE.Intersection,
    form: string,
    marker: Mesh<SphereGeometry | ConeGeometry, THREE.MeshStandardMaterial>
): Mesh

###### **Permet de recréer les marqueurs des topics déjà enregistré**
reCreateMesh(

    viewpoint: Viewpoint,
    form: string,
    color: string,
    name: string,
    date: Date
): Mesh | undefined

###### **Sélectionne le marqueur du topic**
selectMarker(topicId: string): void

###### **Déselectionne le marqueur du topic**
deselectMarker(topicId: string): void

###### **Affiche le label du marqueur**
markerTextHover(mesh: Mesh): void

###### **Emêche d'afficher le label du marqueur**
noHover(): void

###### **Supprime le marqueur du topic**
deleteTopic(topicId: string, scene: Scene): void

###### **Récupère l'index du topic pour trouver le marqueur qui correspond**
getId(topicId: string): number