### Ce composant S'occupe de la gestion d'un arbre proposant les propriétés selon l'organisation de la structure du modèle




###### **attribut fourni en fonction de si le viewer est utilisé pour consulter des fichiers locaux ou pour consulter les fichiers d'un projets et porposer les fonctionnalités associées**
@Input() isLocal?: boolean;

###### **L'index du model**
@Input() selectedModelId?: number;

###### **L'index de l'item**
@Input() selectedItemId?: number;

###### **Le projet**
currentProject: IProject | null | undefined;

###### *À remplir*
treeControl = new NestedTreeControl</SpatialNode>((node) => node.children);

###### *À remplir*
controls = new Map<string, FlatTreeControl</SpatialFlatNode>>();

###### *À remplir*
treeFlattener: MatTreeFlattener<SpatialNode, SpatialFlatNode>;

###### **mapping entre le nom d'un fichier et le mapping entre ses noeuds et le nom qui leur est associé**
treesNodesNames = new Map<string, Map<string, string>>();

###### *À remplir*
sources = new Map<string,MatTreeFlatDataSource<SpatialNode, SpatialFlatNode>()

###### **Contient les noeuds pour générer l'arbre**
spatialTreeDataSource = new MatTreeNestedDataSource</SpatialNode>();

###### **Données de l'arbre**
datas: SpatialNode[]  [];

###### **liste des Id des modèles présents (déjà chargé) au sein de l'API IFC**
- modelsIds$: Observable<(number | undefined)[] | undefined>
- modelIdsSubscription: Subscription | null

###### **Liste des ids observés**
modelsIds: (number | undefined)[] | undefined;

###### **Liste des expressIds utilisé pour la séléction depuis l'arborescence**
expressIds: number[]

###### **Table des subscriptions**
ifcTreeSubscriptions: Subscription[] | null

###### **Mapping entre le nom d'un fichier et la checkList associée**
modelChecklistSelectionMap = new Map<string,SelectionModel</SpatialFlatNode>();

###### **Map from flat node to nested node. This helps us finding the nested node to be modified**
*À traduire*
flatNodeMap = new Map<SpatialFlatNode, SpatialNode>();

###### **Map from nested node to flattened node. This helps us to keep the same object for selection**
*À traduire*
nestedNodeMap = new Map<SpatialNode, SpatialFlatNode>();

###### **Permet d'adapter le traitement de l'arbre en fonction de si la sélection a été faite depuis l'arbre ou le modèle**
selectionFromModel = false;

###### **Fonction de conversion regex**
convertUnicodeFrom2Characters = convertUnicodeFrom2Characters;


Constructeur :
- private BimcloudSpaceService
- private [[Ifc Service]]
- private DbService
- public LoadingService
- public [[Viewer-facade]]
- private ChangeDetectorRef

###### **Permet de retrouver une noeud dans un arbre en fonction de l'expressID de l'item sélectionné**
findSpatialNodeFromItemId(

    rootNodes: SpatialNode[],
    itemId: number,
    computedValue: SpatialNode
): SpatialNode

###### **Recherche le chemin de la node**
findNodePath(

    selectedNode: SpatialNode,
    selectedModelNodes: SpatialNode
): SpatialFlatNode[]

###### **Vérifie si la node possède des enfants**
spatialNodeHasChild = ( _ :number, node: SpatialNode)

###### **Initialisation de l'arborescence avezc l'API sans JSON**
initSpatialTree = async (modelID: number)

###### **Initialise l'arborescence depuis l'arborescence JSON**
async initSpatialTreeFromJsonTree(blob: Blob, viewerFile: ViewerFile)

###### **Initialisation de l'arborescence avec le fichier JSON des propriétés venant du serveur**
initSpatialTreeFromJson = async (viewerFile: ViewerFile)

###### **Initialisation de l'arborescence avec un fichier JSON venant d'indexedDB**
initSpatialTreeFromIdb = async (viewerFile: ViewerFile)

###### **Création d'un noeud de l'arborescence du modèle depuis les données issues du json des propriétés du modèle**
createSpatialNodeFromJson(ifcTree: {

    name?: string;
    expressID: any;
    type: string;
    children: any[];
})

###### **Mise à jour de la structure spatiale lors d'un double clique sur un item du model**
updateSpatialTree = async (id: number, modelID?: number)

###### **Trouver toutes les propriétés IFC répondant à un type dans le JSON**
getAllItemsOfType(type: string, viewerFile: ViewerFile)

###### **Trouver la première propriété IFC répondant à un type dans le JSON**
getFirstItemOfType(type: string, viewerFile: ViewerFile)

###### **Construction du spatial tree à partir du fichier JSON indéxé dans la base de données**
async constructSpatialTreeNodeFromIdb(

    item: any,
    contains: any,
    spatials: any,
    viewerFile: ViewerFile
)

###### **Construction du spatial tree à partir du fichier JSON récupéré sur le serveur**
async constructSpatialTreeNodeFromJson(

    item: any,
    contains: any,
    spatials: any,
    viewerFile: ViewerFile
)

###### **Mise en surbrillance d'un item lors du passage de la souris sur sa représentation dans l'arborescence**
preSelectFromSpatialTree(modelId: number, node: SpatialNode)

###### **Sélection d'un item depuis le spatial tree
Méthode appelé à partir du spatial tree**
selectFromSpatialTree(modelId: number, node: SpatialNode)

###### **Récupère les indexs des enfants**
getChildrenIds(node: SpatialNode)

###### **Récupère le niveau d'une node**
getLevel = (node: SpatialFlatNode)

###### **Vérifie si la node est expensible**
isExpandable = (node: SpatialFlatNode)

###### **Récupère les enfants de la node**
getChildren = (node: SpatialNode): SpatialNode[]

###### **Vérifie si la node possède des enfants**
hasChild = (: number, nodeData: SpatialFlatNode)

###### **Vérifie si la node n'a aucune données**
hasNoContent = (: number, nodeData: SpatialFlatNode)  nodeData.finalName === '';

###### **Transformer to convert nested node to flat node. Record the nodes in maps for later use.** 
*À traduire*
transformer = (node: SpatialNode, level: number)

###### **Checkbox dans le spatial tree**
selectFromSpatialTreeCheckbox(modelId: number, node: SpatialFlatNode)

###### **Séléctionne tous les descendants de la node.**
descendantsAllSelected(node: SpatialFlatNode, modelId: number): boolean

###### **Séléctionne une partie des descendants de la node**
descendantsPartiallySelected(
    node: SpatialFlatNode,
    modelId: number
): boolean

###### **Après un clique sur une case à cocher, séléctionne / déselectionne tous les déscendant de la node**
spatialNodeToggle(node: SpatialFlatNode, modelId: number): void

###### **Checks all the parents when a leaf node is selected/unselected** *À traduire*
checkAllParentsSelection(node: SpatialFlatNode, modelId: number): void

###### **Check root node checked state and change it accordingly** *À traduire*
checkRootNodeSelection(node: SpatialFlatNode, modelId: number): void

###### **Récupère le parent d'une node**
getParentNode(

    node: SpatialFlatNode,
    modelId: number
): SpatialFlatNode | null

###### **Récupère le nom de la propriété via l'IFC**
*Les pertes de performance lors de la création de l'arbre semble venir de cette focntion*
getNamePropertieFromIFC(modelId: number, node: SpatialNode)

###### **Récupère le nom de la propriété via le JSON**
getNamePropertieFromJSON(modelId: number, node: SpatialNode)

###### **Appelé dans la barre de recherche**
public async researchBar(datas: SpatialNode[][] | SpatialNode[])