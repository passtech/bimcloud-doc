### Le coeur de toutes les fonctions du viewer vue qu'il contient l'ifcViewer qui définit toutes la scène, la caméra et le renderer.


**API pour le traitement des fichiers IFC**
ifcViewer?: IfcViewerAPI | null;

**Element dans lequel la scène du viewer sera affichée**
container?: HTMLElement;

**Future fonctionnalité pour l'export de fichier DXF**
dxfWriter: DXFWriter;

**Variable permettant de connaître le status de la préselection**
preSelectionStatus = false;

**Variable permettant de connaître le status de la selection standard**
selectionStatus = false;

**Variable permettant de connaître le status de la selection highlight**
highlightStatus = false;

**Variable qui enregistre quelle mode de selection est en place**
saveStateSelection = 2;

**Définit si les dimensions sont affichable**
dimensionStatus = false;

**Définit si on peut créer des dimensions**
dimensionCreateStatus = false;

**Définit si on peut supprimer des dimensions**
dimensionDeleteStatus = false;


**Contrôle si on peut créer des plans de coupes**
createClipping = false;

**Contrôle si on peut isoler des plans de coupes**
clippingIsolation = false;


**Variable permettant de connaître le mode de projection**
cameraProjection = 0;

**Variable permettant de connaître le mode de navigation**
cameraNavigation = 0;


**Variable utiliser pour les controles du cube**
- cubeControls: CubeControls | undefined;
- cubeOrbitControls: OrbitControls | undefined;
- cubeElement: HTMLElement | undefined;


**Variable permettant de retracer le clique de la souris**
- raycaster = new THREE.Raycaster();
- pointer = new THREE.Vector2();

**Permet de créer un label 2D dans la scène**
labelRenderer: CSS2DRenderer = new CSS2DRenderer();

**Permet de connaître le point centrale de la scène par rapport à tous les models chargés**
centroid: Vector3 = new Vector3(0, 0, 0);

**Model de la projection pour les marqueurs des topics**
projection: Mesh | undefined;

**Forme de la projection**
projectionForm = 'cone';

**Permet de récupérer le nom du model lié à la projection**
projectionFile: ViewerFile | undefined;


**Version du bcf, variable static**
VERSION_BCF = '3.0';

**Tableau des différents callback à appeler lors d'une sélection**
onSelectActions: ((

    id: number,
    modelID?: number,
    viewerFile?: ViewerFile
) => void)[];

ifcProductsType: { [modelID: number]: { [expressID: number]: number } };

**Précisions sur le contexte dans lequel le viewer est utilisé**
- forLocalFiles?: boolean;
- forPrivateProject?: boolean;

**mapping entre le nom d'une catégorie d'objet IFC et la constante associé dans l'API IFC**
readonly categories = IFCCategories;

Constructeur :
- public [[Viewer-facade]]
- private BimcloudSpaceService
- private LangFacade
- private NgrxUploaderFacade
- private FileUploaderService
- private DbService
- public [[Topic Service]]
- private HttpClient
- public [[Viewpoints-service]]


**Ajouter le viewer dans un élément html d'un composant,**
*l'appel à cette méthode doit être suivi d'un startIfcViewer pour finir l'initialisation de l'API IFC*
addViewerInComponent(renderer: Renderer2, element: HTMLElement): void

**Récupère les controleurs du cube**
addCubeInComponent(

    nativeElementContainer: HTMLElement,
    nativeElementCanvas: HTMLCanvasElement
)

**Remise à niveau du viewer pour une nouvelle utilisation**
*l'appel à cette méthode doit être suivi d'un startIfcViewer pour finir la réinitialisation de l'API IFC*
resetViewer(renderer: Renderer2): void

**Initialise le viewer**
startIfcViewer(forLocalFiles?: boolean, forPrivateProject?: boolean): void | Error

**Création des axes et de la grille pour un IFC après initialisation du viewer IFC**
setupIfcScene(): void

**Change le type de sélection en mode standard, highlight ou none**
changeSelectionState(mode: number): void

**Change le status de l'affichage du cube component**
changeCubeStatus(): void

**Change le status de l'affichage des annotations**
changeAnnotationStatus(): void

**Change le status de l'affichage des plans de coupe**
changeClippingStatus(): void

**Supprime un plan de coupe**
deleteClippingPlane(selectedPlane: IfcPlane): void

**Change le status de l'affichage des Dimensions**
changeShowDimensionsStatus(): void

**Change le status du mode de création des dimensions**
changeCreationDimensionStatus(): void

**Change le status du mode de suppression des dimensions**
deleteDimension(): void

**Enlève toutes les dimensions créer**
deleteAllDimension(): void

**Change la langue**
changeLang(lang: string): void

**Récupère l'url du screenshot et l'ajoute aux élements du PDF**
takeScreenshot(): string

**Controle de la caméra**
cameraControl(nav: number): void

**Changement de projection**
changeProjection(proj: number): void

**Visualisation du plan suivant l'index du model
Appelé dans project-viewer pour l'affichage des niveaux**
async viewPlan(modelID: number): Promise<string[] | undefined>

**Pointe la caméra vers le niveau choisie**
async setLookAtFloor(

    modelID: number,
    expressID: string,
    name: string,
    type: string
): void

**Permet de bouger la caméra en appuyant sur z, q, s, d, a ou e.
z et s permette de bouger vers l'avant ou vers l'arrière.
q et d permette de bouger vers la gauche ou vers la droite.
a et e permette de bouger vers le haut ou vers le bas.**
movementFPS(key: string): void

**Permet de calculer le centroid de tous les models présent dans la scène**
calculCentroid(): void

**Initialisation des différents évènements (clique, double clique et mouvement souris)**
setupInputs():  void

**Souscrire aux évènements d'un fichier ifc**
subscribeOnSelect(

    action: (id: number, modelID?: number, viewerFile?: ViewerFile) => void
): void

###### **Sauvegarde les éléments pdf**
savePdfElements(orderElementPdf: Array<{url?: string; name?: string; data?: HTMLTableElement; }>): void

###### **Retourne les éléments pdf**
getPdfElements(): Array<{url?: string; name?: string; data?: HTMLTableElement; }>

**Chargement d'un fichier IFC dans la visionneuse
évènement :**
- **1 - chargement modèle à partir d'un fichier IFC**
- **2 - preprocessing à partir d'un fichier IFC**
- **3 - récupération des nouveaux fichier à partir du projet**
- **4 - récupération du fichier gltf à afficher à partir des fichiers du projet**
- **5 - chargement du modèle à partir du gltf**

**différents cas :**
- **j'ai un IFC local -> 1**
- **j'ai un IFC non-local -> 2 -> 3 -> 4 -> 5**
- **j'ai un gltf -> 5**
loadFile(

    file: File | null | undefined,
    localFile: boolean | undefined,
    privateFile?: boolean,
    projectId?: string,
    storageProvider?: string
): Observable</IFCModel>

**Chargement d'un fichier IFC pour le viewer local (génération du modèle + affichage)**
loadLocalFileIFC(file: File): void

**Chargement d'un fichier IFC pour le viewer d'un projet (preprocessing + récupération gltf)**
loadProjectFileIFC(

    file: File,
    privateFile: boolean,
    projectId: string,
    storageProvider: string
): Observable</IFCModel>

**Chargement d'un fichier GLTF pour le viewer d'un projet (génération du modèle + affichage)**
loadFileGLTF(file: File): Observable</IFCModel>

**Methode de callback permettant de suivre le chargement de l'IFC**
onProgressLoadIfc(progress: ProgressEvent): void

**Permet de mettre à jour manuellement le pourcentage d'avancement
du chargement des modèles.
IFC viewer ne gère que le pourcentage d'avancement du fichier**
progressLoadModel(value: number): void

**Permet de mettre à jour manuellement le status de chargement d'un model**
updateLoadModelStatus(status: string, local?: boolean): void

**Export d'un fichier/modèle au format GTLF vers le serveur de stockage de l'application**
exportGLTF(

    fileIFC: File,
    fileName: string,
    privateFile: boolean,
    projectId: string,
    storageProvider: string
): void

*À remplir*
exportProperties(

    fileIFC: File,
    fileName: string,
    privateFile: boolean,
    projectId: string,
    storageProvider: string,
): 

**Initialisation de l'arborescence avec le fichier JSON des propriétés venant du serveur**
async initSpatialTreeFromJSON(
  
    propertiesFileJSON: any,
    fileName: string
): Promise</File>

**Trouver la première propriété IFC répondant à un type dans le JSON**
getFirstItemOfType(type: string, treeFile: any): : Promise</any>

**Trouver toutes les propriétés IFC répondant à un type dans le JSON**
getAllItemsOfType(type: string, treeFile: File): Promise<any[]>

**Construction du spatial tree à partir du fichier JSON récupéré sur le serveur**
async constructSpatialTreeNodeFromJson(

    item: any,
    contains: any,
    spatials: any,
    properties: any
): void

**Cette fonction génère les fichiers nécessaire au gain de temps de traitement lors de la lecture d'un fichier IFC (fihcier gltf, propriétés au format json, arborescence au format json)**
exportPreprocessingFiles(

    fileIFC: File,
    fileName: string,
    privateFile: boolean,
    projectId: string,
    storageProvider: string,
    replace?: boolean,
    exportTree?: boolean
): Observable<HttpResponse</any>>

**Initialisation de l'arborescence avec un fichier JSON venant d'indexedDB**
async initSpatialTreeFromIdb(viewerFile: ViewerFile): Promise<{  

	name: string;  
	expressID: any;  
	type: string;  
	finalName: string;  
	children: never[];  
} | undefined>

**Construction du spatial tree à partir du fichier JSON indéxé dans la base de données**
async constructSpatialTreeNodeFromIdb(

    item: any,
    contains: any,
    spatials: any,
    viewerFile: ViewerFile
): void

**Methode de callback permettant de suivre les problèmes lors d'un chargement d'un fichier IFC**
onErrorLoadIfc(err: any): void

**Affichage d'un modèle dans le viewer si celui-ci a déjà été généré**
loadModel(modelIndex: number): void

**Création d'un sous-ensemble d'objet d'un même modèle ayant la même catégorie**
async newSubsetOfType(

    categoryKey: string,
    categoryValue: number,
    viewerFile: ViewerFile,
    localFile: boolean
): Promise<Subset | undefined>

**Récupération de tous les items IFC d'un modèle pour une catégorie donnée**
- async getAllItemsOfCategory(

    category: number,
    modelID: number
): Promise<number[] | undefined>
- async getAllItemsOfCategoryFromIdb(

    viewerFile: ViewerFile,
    category: string
): Promise<any[] | undefined>

**Trouver l'index du modèle dans le contexte du viewer en fonction de son uuid**
findModelIndex(modelUUID: string): number | undefined

**Récupération d'un viewerFile (informations complémentaires relatives au modèle) depuis un modelID**
findViewerFileFromModelID(modelID: number): ViewerFile | undefined

**Récupération d'un viewerFile (informations complémentaires relatives au modèle) depuis un nom de fichier**
findViewerFileFromFileName(fileName: string): ViewerFile | undefined

**Masquer un modèle qui a déjà été chargé**
closeModel(file: ViewerFile): void

**Chargement des propriétés contenues dans le fichier json d'un modèle
et indexation dans la base de données**
async loadPropertiesFromJson(

    viewerFile: ViewerFile,
    json: Blob,
    forPreprocessing?: boolean,
    projectId?: string
): Promise</any>

*À remplir*
completeProperty(properties: any, property: any): any

**Récupération des propriétés contenues dans le fichier json**
async readPropertiesFromJson(json: Blob): : Promise</any>

**Chargement des propriétés de l'objet sélectionné à partir du fichier JSON
Lancé par l'action viewerActions.loadSelectedProperty**
loadSelectedItemPropertyFromJson(viewerFile: ViewerFile, expressID: number): void

**Chargement des propriétés de l'objet sélectionné à partir de la base de données IndexeDB
Lancé par l'action viewerActions.loadSelectedProperty**
async loadSelectedItemPropertyFromIdb(

    viewerFile: ViewerFile,
    expressID: number
): void

**Récupère les propriétés d'un projet provenant de BimCatalogue**
getPropertyFromBimCatalogue(

    projectId: string,
    fileName: string,
    expressID: number
): Observable<HttpResponse</any>>

**Récupération de l'ensemble des propriétés à partir du JSON**
getPropertySetsFromJson(props: any, properties: any): any

**Récupération de l'ensemble des propriétés à partir d'IndexedDB**
async getPropertySetsFromIdb(

    props: any,
    viewerFile: ViewerFile
): Promise<any[]>

**Supprime toutes les données relié à l'ifc dans la base de données idb**
async removeIfcRelatedDataFromIdb(fileId: string, json: Blob): void

**Parcourir le tableau des callback et appelle chaque action**
select(

    modelID: number,
    expressID: number,
    onLocalFile?: boolean,
    pick = true
): void

**Change le status de l'isolation des plans de coupe**
isolationStatus(bool: boolean): void

**Sélection d'un élément dans le viewer IFC**
async pick(): void

**Recupère l'intersection entre le raycaster et le model dans la scène**
getIntersec(): THREE.Intersection<THREE.Object3D<THREE.Event>> | undefined

**Créer un marqueur dans la scène**
renderMarker(

    form: string,
    color: string,
    title: string,
    projectName?: string,
    date?: Date
): {

	marker: Mesh<THREE.BufferGeometry, THREE.Material | THREE.Material[]>;  
	camera: THREE.Camera;  
} | undefined

**Supprime la projection du marqueur**
deleteProjection(): void

**Vérifie si le marqueur du topic doit être recréer**
checkRecreateTopic(topic: Topic, date: Date): void

**Supprime le marqueur du topic**
deleteMarker(topic: Topic): void

**Permet de créer une projection du marqueur**
projectMarker(): void

**Vérifie si la projection à été créer**
checkProjection(): boolean

**Permet de bouger la camera vers la position du viewpoint**
moveCameraToImage(viewpoint: Viewpoint): void

**Permet de changer la rotation de la caméra**
*----- LES FONCTIONS CalculAzimuth ET CalculPolar DOIVENT ÊTRE RÉPARÉ POUR QUE CETTE FONCTION SOIT UTILISÉ -----*
changeRotationCamera(): void

**Calcule de l'angle Azimuth qui permet de faire tourner horizontalement la caméra
Pour plus d'information sur le processus, visiter se forum: https://openclassrooms.com/forum/sujet/calcul-dangles-a-partir-de-3-landmarks-x-y-z**
*----- LA FONCTION NE MARCHE PAS -----*
CalculAzimuth(position: Direction, rotation: Direction): number

**Calcule de l'angle Polar qui permet de faire tourner la caméra verticalement.
Pour plus d'information sur le processus, visiter se forum: https://openclassrooms.com/forum/sujet/calcul-dangles-a-partir-de-3-landmarks-x-y-z**
*----- LA FONCTION NE MARCHE PAS -----*
CalculPolar(position: Direction, rotation: Direction): number

**Change le status de l'affichage de la projection du marqueur**
changeProjectionState(bool: boolean): void

**Evenement lorsqu'il y a un clique dans le container du viewer
Sélectionne un élément sur la visonneuse
Ferme la modal du context menu si elle est ouverte**
private handleClick = async (event: MouseEvent): void

**Évenement déclenché lorsque l'on clique dans le cube viewer**
private handleCubeClick = async (): void

**Lorsque le click est enclenché, on actives les fonctions dans la boucle**
private handleMouseDown = async (): void

**Affichage d'un menu contextuel quand il y a un clic droit**
private handleContextMenu = async (event: Event): void

**Evenement lorsqu'il y a un double clic dans le container du viewer**
async handleDoubleClick = (): void

**Evenement lorsqu'il y a il y a passage de la souris dans le container du viewer**
private handleMouseMove = (event: MouseEvent): void

**Evenement lorsqu'il y a il y a passage de la souris**
private handleGlobalMouseMove = (): void

**Peut-importe ou le clique se fait, cette évènement se déclenche**
private handleGlobalClick(): void

**Méthode retournant une erreur si l'item de la visionneuse n'est pas trouvé**
private notFoundError(item: string): void