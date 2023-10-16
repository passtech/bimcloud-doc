Ce composant affiche toutes les informations des annotations enregistré dans le projet.

@Input() project: Project;

Variables stockant les options des graphiques qui leurs sont associés
GRAP_RADUIS: number[] = [80, 100];

BASE_GRAPH_OPTIONS: EChartsOption = {

    tooltip: {
      trigger: 'item',
      formatter: '{a} <br/>{b} : {c} ({d}%)',
    },
    calculable: true,
    series: [
      {
        name: 'area',
        type: 'pie',
        radius: this.GRAP_RADUIS,
      },
    ],
};

statusOptions: EChartsOption = {};

priorityOptions: EChartsOption = {};

typeOptions: EChartsOption = {};

Variables stockant le thème des graphiques qui leurs sont associés
priorityTheme = { color: ['#C6C6CF', '#40A9E1', '#F7C81E', '#ED190C'] }
statusTheme = { color: ['#C6C6CF', '#40A9E1', '#F7C81E', '#ED190C'] }
typeTheme = { color: ['#C6C6CF', '#40A9E1', '#F7C81E', '#ED190C'] }

Permet de connaître la langue choisie par l'utilisateur
currentLang: string

Permet de stocker tous les subscribe
subscriptions: Subscription[]

Stocke tous les topics. localTopics est modifiable. baseLocalTopics n'est pas modifiable.
localTopics: Topic[]

baseLocalTopics: Topic[]

Stocke l'ordre actuel des topics.
orderMode = 0;

Si true, affiche le container des filtres
isFiltered = false;

Permet de stocker le titre rechercher dans la barre de recherche.
searchedTitle = '';

Stocke les filtres renseigné dans le contained des filtres

  filters = {

    priority: 'No-priority',
    status: 'No-status',
    type: 'No-type',
    isDate: false,
    creationDate: new Date(),
};

Informations affichées dans la table de la liste des fichiers
displayedColumns: string[] = [

    'Image',
    'Title',
    'CreatedBy',
    'CreationDate',
    'LastModifiedDate',
    'Priority',
    'Status',
    'Type',
    'Comments',
];

Services utilisé :
- LangFacade
- [[Topics-service]]
- BCFBIMCloudService
- [[Ifc Service]]
- ChangeDetectorRef
- TranslatePipe
- [[Viewpoints-service]]
- Router
- ActivatedRoute


Initialise tous les graphiques
initGraphs(): void

Simule un clique sur l'input.
openFile(fileInput: HTMLInputElement): void

Importe un fichier BCF
importBCF(e: any): void

Export un fichier BCF
exportBCF():void

Lors d'un click sur un des graphiques, change le filtre associé au graphique
onPriorityChartClick(e: any); void
onStatusChartClick(e: any): void
onTypeChartClick(e: any): void

Change le mode de filtrage
changeOrderFilter(mode: number)

Change le mode de triage des topics
orderFilter(): void

Change les filtres de la priorité, du status, du type et de la date lorsque l'on appuie sur le bouton rechercher dans la fenètre des filtres.
changeElementFilter(reset?: boolean): void

Récupère le titre insérer dans la barre de recherche
getSearchedTitle(e: any): void

Filtre les topics
FilterTopics(closeWindow?: boolean): void

Active/Désactive la fenètre des filtres
showFilters(): void
hideFilters(): void

Change la route vers le [[Project-viewer]] en établissant un chemin vers le composant [[Topics-list]]
viewTopic(topicId: string): void