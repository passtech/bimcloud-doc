### Ce composant permet d'enregistrer les modèles et de les affichées dans le viewer.


###### *À remplir*
@Input() isLocal?: boolean;

###### **Le projet actuellement utilisé**
- currentProject$?: Observable<IProject | null | undefined>;
- currentProject: IProject;

###### *À remplir*
@Input() isPublic = false;

###### **Définit si le composant est encore en train de charger ses données**
@Input() isLoading = false;

###### **Les fichiers disponible dans le [[Viewer-facade]]**
files$: Observable<Record<string, ViewerFile | undefined>>;

###### **Permet de charger le premier fichier du projet**
isFirst = false;

###### **Suit le status du chargement des propriétés du model dans IndexedDB**
propertiesIndexationInProgress$: Observable<boolean | undefined>;

###### **Définit les propriétés du loader**
propertiesLoaderData: LoaderData = new LoaderData();

###### *À remplir*
currentFileLocal?: File | null;

###### **Table des subscriptions**
subscriptionArr: Subscription[]
###### **Contrôle pour l'import des données d'un projet**
@ViewChild('fileInput') fileInput!: ElementRef;

Constructeur :
- private [[Ifc Service]]
- private [[Viewer-facade]]


###### **Chargement d'un fichier ifc sur la visionneuse en local**
loadIfc(event: any): void

###### **Ouvre l'explorateur de fichier**
openFile(fileInput: HTMLInputElement)

###### **Visualisation d'un fichier dans le viewer**
public viewProjectFile(viewerFile: ViewerFile | undefined)

###### **Visualisation d'un fichier local dans le viewer**
public viewLocalFile(viewerFile: ViewerFile | undefined)

###### **Supprime un fichier local du store**
*manque: suppression du modèle si affiché + ré-import d'un fichier*
removeLocalFile(

    localFile: File | null | undefined,
    viewerFile: ViewerFile | undefined
)