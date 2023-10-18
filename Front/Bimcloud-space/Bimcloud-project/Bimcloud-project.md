### Ce composant permet d'afficher un projet sous plusieurs formes.

Composant lié :
- [[Project-dashboard]]
- [[Project-members-management]]
- [[Project-topic]]
- [[Edit-project]]



###### **Informations relatives au projet sélectionné**
- project: Project;
- projectTags: Tag[];
- projectId: string;
- spaceName: string;
- toRemoveDate: Date;

###### **Compte de l'utilisateur courrant pour appliquer la gestion des rôles**
- currentAccount: Account;
- roleProjectAdmin: string;
- roleProjectUser: string;
- roleProjectVisitor: string;

###### **fichiers du projet**
- files: BimCloudFile[];
- filesDataSource: MatTableDataSource</BimCloudFile>;

###### **Mapping entre le nom d'un fichier et les différents format existant pour ce nom**
existingFormat: Map<string, string[]>;

###### **Informations affichées dans la table de la liste des fichiers**
displayedColumns: string[] = [

    'name',
    'size',
    'createdBy',
    'storedWith',
    'lastModifiedBy',
    'lastModifiedDate',
    'privateFile',
    // 'availableFormat', // colonne listant les différents format disponible pour un même fichier
    'actions',
];

###### **Fournisseur de stockage externes paramétrés par l'utilisateur**
public userStorageProviders: IdentityProviderAccount[];

###### **Solutions de stockages proposées par l'application**
storageProviders: Provider[];

###### **Solution de stockage sélectionnée**
storageProvider: Provider;

###### **Fichier en cours d'édition**
currentFile: BimCloudFile;

###### **Selection d'un viewer suivant son type**
viewer: string;

###### **Nom du projet formaté pour les rôles**
projectNameForRoles: string;

###### **Selecteur de fournisseur de service :**
- readonly providerIconsMap = new Map<Provider, IconDefinition>([

    [Provider.DROPBOX_STORAGE, faDropbox],
    [Provider.GOOGLE_DRIVE_STORAGE, faGoogleDrive],
    [Provider.ONEDRIVE_STORAGE, faMicrosoft],
    [Provider.AMAZON_S3_STORAGE, faAmazon],
    [Provider.AUTODESK_OAUTH, faHome],
    [Provider.LOCALHOST_STORAGE, faServer],
    [Provider.SFTP_STORAGE, faServer],
    [Provider.FTPS_STORAGE, faServer],
]);
- readonly providerTextMap = new Map<Provider, string>([

    //[Provider.DROPBOX_STORAGE, 'global.providers.dropbox'],
    [Provider.GOOGLE_DRIVE_STORAGE, 'global.providers.google-drive'],
    // [Provider.ONEDRIVE_STORAGE, 'global.providers.onedrive'],
    // [Provider.AMAZON_S3_STORAGE, 'global.providers.amazon-s3'],
    // [Provider.AUTODESK_OAUTH, 'global.providers.autodesk'],
    [Provider.LOCALHOST_STORAGE, 'global.providers.local-storage'],
    // [Provider.SFTP_STORAGE, 'global.providers.sftp'],
    // [Provider.FTPS_STORAGE, 'global.providers.ftps'],
]);

###### **Contrôle le formulaire des tags**
tagCtrl = new FormControl('');

###### **Liste des tags disponible (à récupérer sur le serveur)**
filteredTags$: Observable<Tag[]>;

###### **Détermine si l'input pour créer un nouveau tag doit être affiché**
tagInput: boolean;

###### *À remplir*
separatorKeysCodes: number[] = [ENTER, COMMA];

###### **Une vue sur le formulaire des tags**
@ViewChild('tagFormInput') tagFormInput: ElementRef</HTMLInputElement>;

###### **La valeur présente dans l'input du formulaire des tags**
tagInputValue: string;

###### *À remplir*
randomForRefresh: number;


constructeur:
- @Inject(ENV_INJECTION) private envInjection: any,
- private authFacade: AuthFacade,
- private userService: UserService,
- private bimcloudSpaceService: BimcloudSpaceService,
- private ifcService: [[Ifc Service]],
- private importProjectFileDialog: MatDialog,
- private removeProjectOptionsDialog: MatDialog,
- public loadingService: LoadingService,
- private activatedRoute: ActivatedRoute,
- public editProjectDialog: MatDialog,
- private importImageDialog: MatDialog,
- private editFileAddress: MatDialog,
- private router: Router,
- private stateSessionStorageService: StateSessionStorageService


###### **Récupération des informations relatives à un projet**
public getProject(): void

###### **Import d'un fichier vers le serveur**
addProjectFile(): void

###### **Suppression d'un fichier sur le serveur**
removeProjectFile(

    filePath: string,
    fileName: string,
    fileType: string,
    fileId: string,
    projectId: string
): void

###### **Visualisation d'un fichier dans le viewer**
public viewProjectFile(file: BimCloudFile): void

###### **Vérifie si un provider à été créer par l'utilisateur**
isProviderProvided(provider: Provider): boolean

###### **A remplacer par un get user contentant les infos providers**
changeStorageProviderInUse(newProviderInUse: Provider): void

###### **Ouverture d'un dialogue pour modifier les informations du projet**
openEditDialog(): void

###### **Changment de la visibilité d'un fichier (privé/public)**
updateFilePrivacy(file: BimCloudFile): void

###### **Génération et transmition au serveur des fichiers gltf et json associés au modèle ifc**
exportPreprocessingFiles(file: BimCloudFile): void

###### **Vérifie si un fichier est en train d'être prétraité**
isFileAlreadyPreprocessed(file: BimCloudFile): boolean

###### **Permet d'aller dans le [[Project-viewer]] pour ouvrir le fichier choisis dans la scène**
viewFile(file: BimCloudFile): void

###### **Permet de télécharger le fichier**
downloadFile(file: BimCloudFile): void

###### **Refraichissement de la liste en cas de décalage entre l'affichage et le contenu du serveur**
refreshProjectFileList(projectId: string): void

###### **Vérifie les authorisations du compte**
currentAccountHasAuthority(authority: string): void

###### *À remplir*
adaptProjectNameForRole(projectName: string): void

###### **Ajoute un nouveau tag lorsque le composant est fermée**
addTag(event: MatChipInputEvent): void

###### **Ajoute un nouveau tag**
validateTagInput(): void

###### **Ajoute une des options de tag généré lorsqu'elle sont séléctionner**
selected(event: MatAutocompleteSelectedEvent): void

###### **Supprime un tag sur le projet local**
removeTag(tag: Tag): void

###### **Supprime un tag sur le projet enregistrer dans la BDD**
*removeTag et removeProjectTag doivent être combiné*
removeProjectTag(tag: Tag): void

###### **Modifie un tag**
editProjectTag(tag: Tag, event: MatChipEditedEvent): void

###### **Sauvegarde l'url actuellement utilisé comme étant la dernière url**
saveCurrentUrlAsLastUrl(): void

###### **Modifie le logo du projet**
editProjectLogo(): void

###### **Active la modification du logo**
enableEditLogo(): void

###### **Désactive la modification du logo**
disableEditLogo(): void

###### **Annule la suppression du projet**
cancelRemove(): void

###### **Ouvre un MatDialog sur la suppression du projet**
public commentProjectRemove(forAdmin: boolean): void

###### **Remet à jour le projet**
redoProject(): void

###### **Ouvre un MatDialog sur l'address du fichier choisis**
openEditAddressDialog(file: BimCloudFile): void