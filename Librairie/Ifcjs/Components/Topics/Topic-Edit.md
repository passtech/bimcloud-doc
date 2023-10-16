### Ce composant sert à modifié le topic choisis dans le [[Topic-viewer]].


###### **Le topic choisis**
@Input() localTopic: Topic | undefined;

###### **L'index du topic choisis**
@Input() localTopicId: number | undefined;

###### **Émetteur communiquant la fin de l'édition**
@Output() closeEmitter = new EventEmitter</boolean>();

###### **Émetteur communiquant l'annulation de l'édition**
@Output() cancelEmitter = new EventEmitter</Topic>();

###### **Le topic de base en cas d'annulation de l'édition.**
baseLocalTopic: Topic | undefined;

###### **Le viewpoint de base en cas d'annulation de l'édition**
baseLocalViewpoint: Viewpoint | undefined;

###### **Le nouveau viewpoint pour le topic**
localViewpoint: Viewpoint | undefined;

###### **S'enclenche si le titre n'est pas renseigner.**
titleRedText: boolean

###### **Contrôle si on peut créer une projection du topic sur les modèles**
isProjected: boolean

###### **Table des subscriptions**
subscription: Subscription[]


Constructeurs :
- private [[Topics-service]]
- private [[Ifc Service]]
- private ChangeDetectorRef
- private [[Topic Service]]
- private [[Viewpoints-service]]


###### **Récupère le viewpoint du topic et créer le topic et le viewpoint de base en cas d'annulation de l'édition**
initEdition(): void

###### **Active ou non la possibilité de placer une projection du marqueur du topic sur les modèles**
changeProjectionState(bool: boolean): void

###### **Permet de créer et d'enregistrer le nouveau topic (la manière diffère si le viewer est le viewer local ou un viewer privé/publique)**
createEditTopic(): void

###### **Arrète l'édition du topic et remet les valeurs de bases**
cancelEditTopic(): void

###### **Récupère un screenshot et créer le viewpoint**
getScreenshot(): void

###### **Supprime le viewpoint**
deleteScreenshot(): void

###### **Change la forme du marqueur**
changeFormMarker(): void

###### **Change la couleur du marqueur**
changeColorMarker(): void

###### **Supprime la projection du marqueur**
deleteProjection(): void