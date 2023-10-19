### Ce composant permet d'afficher les informations d'un espace (membres, projets, decription...)



###### **Contrôle pour l'import des données d'un projet**
@ViewChild('fileInput') fileInput: ElementRef;

###### **L'espace représenté par le composant**
- space$: Observable</Space>;
- space: Space;

###### **Id de l'espace issu de l'url**
spaceId: string;

###### **Nom de l'espace formaté pour la gestion des rôles**
- spaceNameForRoles: string;
- roleSpaceAdmin: string;
- roleSpaceUser: string;
- roleSpaceVisitor: string;

###### **Ensemble des projets gérés dans cet espace**
projects: Project[] = [];

###### **Choix de l'affichage de la liste des projets**
projectListAsGrid: boolean;

###### **Utilisateur courrant, utilisé pour la gestion des rôles**
currentAccount: Account;

###### **Mapping projet -> lien vers la page du projet**
projectsUrls: Map<string, string> = new Map();

###### **Informations affichées dans la table de la liste des fichiers**
displayedColumns: string[] = [

    'Title',
    'Members',
    //'CreationDate',
    //'LastModifiedDate',
    'Storage',
    'Public',
    'NbTopics',
    'View',
    // 'availableFormat', // colonne listant les différents format disponible pour un même fichier
];

###### **Le nombre de colonnes requis pour l'affichage des projets**
cols = 4;

###### *À remplir*
private layoutChangesSubscription: Subscription;

###### *À remplir*
randomForRefresh: number;


constructor :
- @Inject(ENV_INJECTION) private envInjection: any,
- private SpaceService
- private BimcloudSpaceService
- private [[Ifc Service]]
- public LoadingService
- private authFacade: AuthFacade,
- private addProjectDialog: MatDialog
- public projectViewerDialog: MatDialog
- public infoProjectDialog: MatDialog
- public removeProjectDialog: MatDialog
- private Router
- private NgrxAlertFacade
- private StateSessionStorageService
- private ProjectService
- private BreakpointObserver
- private importImageDialog: MatDialog


###### **Requête serveur pour récupérer les informations de l'espace**
public getSpace(): Observable</Space>

###### **Requête serveur pour récupérer la liste des projets de l'espace en fonction de son nom**
public getSpaceProjects(spaceName: string): void

###### **Vérification des autorisations de l'utilisateur selon ses rôles**
currentAccountHasAuthority(authority: string): boolean

###### **Ouverture d'une boîte de dialog pour l'ajout' d'un projet à l'esapce courrant**
addProject(): void

###### **Import de projet(s) depuis un fichier ZIP**
*@TODO*
- **définir le format json exact et l'arborescence**
importProjects(): void

###### **Ouvre la dialog pour l'affichage des informations d'un projet**
openDialogInformationProject(project: Project): void

###### **Ouvre le dialog de suppression d'un projet**
openRemoveProjectDialog(project: Project): void

###### **Passage d'un affichage à l'autre pour la liste des projets (liste -> grille ou grille -> liste)**
changeProjectListView(bool: boolean): void

###### **Adapte le nom d'un espace au format des rôles (ROLE_SPACE_XXX_YYY où XXX est le niveau du rôle ADMIN/USER/VISITOR et YYY le nom de l'espace  )**
adaptSpaceNameForRole(spaceName: string): void

###### **Récupération de l'id de l'espace depuis l'url**
getCurrentSpaceId(): string

###### **Sauvegarde l'url actuelle comme étant la dernière url utilisé**
saveCurrentUrlAsLastUrl(): void

###### **Appelé à chaque changement de taille de l'écran permettant de déterminer le nombre de carte projet**
onResized(state: BreakpointState): void

###### **Ouvre le dialog de modification d'un logo**
editSpaceLogo(): void