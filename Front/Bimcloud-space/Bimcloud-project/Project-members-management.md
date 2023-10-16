Ce composant permet de gérer les membres du projet.



Récupère le nom du projet
@Input() projectName: string;

Emetteur qui permet de recréer le projet via la fonction redoProject de [[Bimcloud-project]]
@Output() projectEmitter = new EventEmitter();

Table des membres
members: User[]

Tables des différents types de membres
adminMembers: User[]
userMembers: User[]
visitorMembers: User[]

L'index du projet
projectId: string;

projectNameForRoles: string;

Contrôle si l'écran est grand ou petit (défaut: grand)
isLarge = true;
isSmall = false;



Services utilisé:
- BimcloudSpaceService
- MatDialog
- ActivatedRoute



Récupère les membres du projet et les ranges par type de droit
getProjectMembers(): void

Récupère l'index du projet
getCurrentProjectId(): string

Récupère le nom du projet
getCurrentProjectName(): string

Change le role d'un membre
changeMemberRole(userLogin: string, userProjectRole: string, newUserProjectRole: string): void

Vérifie si l'utilisateur à l'authorité nécéssaires
userHasAuthority(user: User, authority: string): boolean

Ouvre le matDialog pour ajouter un membre
addMember(): void

Supprime un membre du projet
removeMember(userLogin: string, userProjectRole: string, projectId: string): void

Adapte le nom du projet au format des noms des rôles
adaptCurrentProjectNameForRole(): string

Lors d'un changement de taille de la fenètre, vérifie la nouvelle taille de la fénètre.
@HostListener('window:resize', ['$event'])
checkScreenWidth()