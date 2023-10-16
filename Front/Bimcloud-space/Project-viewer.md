Ce composant permet d'afficher le viewer ainsi que toutes les fonctions présentes dans les composants de la librairie IfcJs.

Composant Importés :
- [[Ifcjs-viewer]]
- [[Import-file]]
- [[Spatial-tree]]
- [[Categories]]
- [[Properties-table]]
- [[Clipping-plans]]
- [[Reports]]
- [[Export-dxf]]
- [[Change-parameters]]
- [[Floor]]
- [[Dimension]]
- [[Topics-list]]



Liste des booleans pour l'affichage des cards de la toolbar :
- isListFiles: boolean;
- isHierarchy: boolean;
- isCategories: boolean;
- isProperties: boolean;
- isClippingPlans: boolean;
- isReports: boolean;
- isExportDXF: boolean;
- isHierarchyMinimize: boolean;
- isCategoriesMinimize: boolean;
- isPropertiesMinimize: boolean;
- isPublic: boolean;
- isParameter: boolean;
- isFloor: boolean;
- isDimensions: boolean;
- isTopic: boolean;
  
Contient le global id d'une propriété
currentGlobalId: string;

Le nom de l'objet courrament sélectionné
currentItemName: string;

Si l'affichage de la dialog provient du header (true) ou d'un projet (false)
isLocal: boolean;

Projet courant
currentProject$: Observable</IProject>
currentProject: IProject

Index du projet courant
currentProjectId: string

Table des niveaux
floors: Array<{

    id: number;
    name: string;
    type: string;
    viewerFile?: ViewerFile;
    labels: Array<{ expressid: string; attr: string; name: string }>;
}>

isPlanView: boolean;

Contrôle si les composants nécéssitant des modèles sont activable ou pas
freezeStatus: boolean

Contrôle l'affichage des annotations
annotationStatus$: Observable</boolean>;

Suit le status de chargement du model afin de fournir des informlations relative
à l'évolution du chargement
loadModelStatus$: Observable</string>;

Suit le status du chargement d'un model
isLoading$: Observable</boolean>;

Suit le status de l'indéxation des propriétés
propertiesIndexationInProgress$: Observable</boolean>;

Pourcentage de chargement du viewer
currentProgress$: Observable</number>;
currentLocalSubscription: Subscription;

Permet de savoir si l'utilisateur est connecté
isConnected$: Observable</boolean>;

Détermine si le container de gauche est visible
isLeftTableOn: boolean

Détermine si le container de droite est visible
isRightTableOn: boolean

Détermine si les toolbars sont visible
isToolbar: boolean

selectedModelId$: Observable<number | null | undefined>;
selectedModelId: number;

selectedItemId$: Observable<number | null | undefined>;
selectedItemId: number;

openPropertiesTable$: Observable</boolean>;

openedFrom: string;

Contrôle l'affichage de l'axe et de la grille
axesStatus = true;
gridStatus = true;

L'index d'un topic transmit depuis [[Reports]] ou [[Project-topic]] jusqu'à [[Topics-list]]
localTopicId: string | undefined = undefined;

Input servant à communiquer le status du cube component
@Input() cubeStatus$: Observable</boolean>;


Services utilisé :
- [[Ifc Service]]
- Router
- ActivatedRoute
- [[Viewer-facade]]
- AuthFacade
- Renderer2
- StateSessionStorageService
- [[Preferences Service]]
- NgZone
- ChangeDetectorRef


Initialisation du viewer avec les paramètres reçus en statique dans la déclaration
de la route ou bien dans l'url
initViewer()

Récupère l'index d'un topic provenant de [[Project-topic]] et ouvre le composant [[Topics-list]]
receiveGoToTopics(topicId: string)

updateModelId()

updateItemId()

Liste des fonctions permettant d'ouvrir un composant :
- openListFiles()
- openHierarchy()
- openCategories()
- openProperties()
- openClippingPlans()
- openReports()
- openExportDXF()
- openParameters()
- openFloor()
- openDimension()
- openTopic()

Affiche une annotation faisant office de label pour les boutons du project-viewer
openAnnotation(event: Event)


Liste des fonctions permettant de minimiser un composant :
- minimizeHierarchy()
- minimizeCategories()
- minimizeProperties()

Détecte lorsqu'une touche est pressé et envoie le nom de cette touche dans la fonction "movementFPS" de ifcService.
@HostListener('window:keydown', ['$event'])

Lorsque la souris sort d'un élement ne possédant pas la classe "noTitle" et est de type Anchor, svg, path ou polygon,
alors le conteneur "indication" devient invisible.
@HostListener('document:mouseout', ['$event'])

Au movement de la souris,
le conteneur "indication" change sa marge du dessus et de gauche dépendant de la position de la souris.
@HostListener('mousemove', ['$event'])

Change le freezeStatus si aucun model est affiché
changeAccess()

Récupère l'index d'un topic provenant de [[Reports]] et ouvre le composant [[Topics-list]]
redirectionFromReports(topicId: string)

Réinitialise l'index d'un topic stocké
resetLocalTopicId(): void

Active/Désactive l'axe/la grille
axes(): void
grid(): void

Active/Désactive la séléction standard/ le highlight
Selection(): void
Highlight(): void

Change les contrôles de la caméra
cameraControl(nav: number): void

Change la projection de la caméra
changeProjection(proj: number): void


getCurrentGlobalId(globalId: string): void


getCurrentItemName(currentItemName: string): void

Fermeture du viewer
closeViewer(): void

Permet de centrer la caméra sur le centroïd de la scène
centerOrbit(): void