### Ce composant représente la scène du viewer.


###### **Viewer container permettant d'afficher le viewer**
@ViewChild('viewerContainer', { static: true }) viewerContainer?: ElementRef;

###### **Cube container**
@ViewChild('cubeContainer', { static: true }) cubeContainer?: ElementRef;
@ViewChild('cubeControl', { static: true }) cubeControl?: ElementRef;

###### **permet selon le contexte de définir s'il est possible d'enregistrer un fichier et de le charger à partir du serveur(false) ou de le charger directement depuis les fichiers locauxsans enregistrer (true)**
@Input() isLocal?: boolean

###### **Contrôle l'affichage du cube**
@Input() cubeStatus?: boolean;

###### **Permet d'ouvrir le menu contextuel**
currentContextMenu$: Observable<ContextMenu | undefined>;

Constructeur :
- public [[Ifc Service]]
- private [[Viewer-facade]]
- private Renderer2
- private [[Preferences Service]]


###### **Chargement d'un conteneur HTML et de la visionneuse**
initViewer(): void

###### **Désactive l'affichage du cube**
clearCube(): void

###### **Active l'affichage du cube**
replaceCube(): void

###### **Charger un fichier ifc dans le viewer**
viewProjectFile(file: ViewerFile): void

###### **Charge un fichier local avec la visionneuse en état local**
viewLocalFile(file: File): void