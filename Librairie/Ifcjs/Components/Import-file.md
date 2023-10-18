### Ce composant permet d'enregistrer les modèles et de les affichées dans le viewer.



@Input() isLocal?: boolean;

###### **Le projet actuellement utilisé**
- currentProject$?: Observable<IProject | null | undefined>;
- currentProject: IProject;


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


currentFileLocal?: File | null;

###### **Table des subscriptions**
subscriptionArr: Subscription[]
###### **Contrôle pour l'import des données d'un projet**
@ViewChild('fileInput') fileInput!: ElementRef;

Constructeur :
- private [[Ifc Service]]
- private [[Viewer-facade]]
