Ce composant génère des rapports pour chaque modèles, permet de prendre des captures d'écran de la scène et permet de générer un pdf à partir des rapports et des captures d'écrans.

Le composant est divisé en quatre composant :
- [[Reports]]
- [[Report-details]]
- [[Report-topics]]
- [[Report-pdf]]

Récupération du project id via le [[Project-viewer]]
@Input() projectId = '';

Emitter servant à rediriger l'utilisateur à un topic précis.
@Output() redirectEmitter = new EventEmitter</string>();

 Suit qu'elle tableau doit être ouvert :
   - 0 : Rapports
   * 1 : Topics
   * 2 : Détailles
   * 3 : Export PDF
switchTable: number

Stocke les élements pdf choisis
orderElementPdf: Array<{

    url?: string;
    name?: string;
    data?: HTMLTableElement;
}>

Stockage des données affichées dans le tableau

datas: Array<{

    name: string;
    uuid: string;
    lastModDate: any;
    size: number;
    nameOctets: string;
    categories: Array<{
      type: string;
      number: number;
      details: Array<{
        type: string;
        predefinedType?: string;
        number: number;
      }>;
    }>;
    nbMarkers: number;
    isDetails: boolean;
}>

Permet de filtrer les tables
filterCategoriesTable: string[]
filterAffectedTables: string[]
filterByLevel: number[]

Permet d'aider à filtrer les tables par niveau
countedLevel = 0

Permet de créer les checkboxs
filterCategoriesCheckbox: string[]
filterLevelsCheckbox: number[]

Pré-chargement des Topics pour le composant [[Report-topics]]
localTopics: Topic[]

Filtre des voyels pour la langue française
vowelsFilter = ['a','e','i','o','u'];

Langue actuellement utilisé par l'utilisateur
currentLang = '';

Table des subscriptions
subscriptions: Subscription[]

Services utilisé :
- [[Viewer-facade]]
- [[Ifc Service]]
- ChangeDetectorRef
- [[Topic Service]]
- LoadingService
- BimcloudSpaceService
- [[Topics-service]]
- [[Comments-service]]
- LangFacade
- TranslatePipe


Change la table actuellement utilisé
changeTable(table: number): void

Récupère toutes les données nécéssaires pour créer un rapport pour chaque model chargé
refresh(): void

Récupère le nom du rapport pour ensuite l'ajouter au stockaage des rapports
saveToPDF(name: string): void

Envoi l'élément ifc dans la fonction checkTypeIfc. Si l'élément ifc à des enfants, ils passent tous dans la fonction goThroughtIfc.
goThroughtIfc(ifc: any, name: string, modelID: number): void

Vérifie quelle est le type de l'ifc et incrémente le nombre relié au type.
Créer une nouvelle catégorie détaille si l'élément est une nouvelle version d'un type déjà enregistré.
checkTypeIfc(ifc: any, modelID: number): void

Vérifie quelle est le type du gltf et incrémente le nombre relié au type.
Créer une nouvelle catégorie détaille si l'élément est une nouvelle version d'un type déjà enregistré.
checkTypeGltf(

    type: string,
    gltf: any,
    categories: Array<{
      type: string;
      number: number;
      details: Array<{
        type: string;
        predefinedType?: string;
        number: number;
      }>;
    }>
): void

Vérifie si un nouveau type d'élément doit être ajouter au filtrage des éléments.
checkTypeFilter(model: any): void

Ouvre le tableau des filtres
openFiltre(): void

Ferme le tableau des filtres
closeFiltre(): void

Change les éléments affécter par le filtre
changeTableFilter(event: Event, categorie: string): void

Change les tables affécter par le filtre
changeAffectedTables(event: Event, name: string): void

Change les niveaux affécter par le filtre.
changeAllowedLevels(event: Event, selectedLevel: number): void

Vérifie si le type de l'élément commence par une voyelle
checkVowel(type: string): boolean

Récupère les éléments pdf provenant de [[Report-pdf]]
receiveOrderEmit(

    orderElement: Array<{
      url?: string;
      name?: string;
      data?: HTMLTableElement;
    }>
): void

Récupère la liste des topics présent dans le projet
getTopics(): void

Récupère les éléments pdf provenant de [[Report-topics]]
receiveSaveEmit(

    newOrderElementPdf: {
      url?: string;
      name?: string;
      data?: HTMLTableElement;
    }[]
)

Redirige l'utilisateur vers le topic choisis
redirectToTopic(topicId: string)