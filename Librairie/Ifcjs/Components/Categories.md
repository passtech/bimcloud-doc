### Ce composant permet de filtrer tous les éléments d'un model charger dans le viewer en plusieurs catégories.



###### **Attribut fourni en fonction de si le viewer est utilisé pour consulter des fichiers locaux ou
pour consulter les fichiers d'un projets et porposer les fonctionnalités associées**
@Input() isLocal?: boolean;

###### **Le projet**
@Input() publicProject?: boolean;

###### **Mapping entre le nom d'une catégorie d'objet IFC et la constante associé dans l'API IFC**
readonly categories = IFCCategories;

###### **Mapping entre le nom d'un fichier (ex: 01.ifc -> 01) et les subsets qui lui sont associé par catégories**
fileSubsets = new Map<string, Map<number, Subset>>([]);

###### **Mapping entre le nom d'une catégorie et les Ids des éléments appartenant à cette catégorie
Les catégories sont ici séparées par fichiers, ex: on retrouve les clés 01:IFCWALL et 02:IFCWALL**
categoryItems = new Map<string, number[]>([]);

###### **Mapping entre les items de tous les subsets et leurs status (affiché ou non)**
areItemsDisplayed = new Map<string, boolean>([]);

###### **Mapping entre l'ID d'un item et son LongName dans les propriétés**
itemsNames = new Map<string, string>([]);

###### **Liste des Id des modèles présents (déjà chargé) au sein de l'API IFC**
- modelsIds$: Observable<(number | undefined)[] | undefined>; // id des modèles
- modelIdsSubscription: Subscription | null = null;

###### **Liste des ids observés**
modelsIds: (number | undefined)[] | undefined;

###### **Gestion des checkboxs des models**
checkModelSelection = new SelectionModel</string>(true);

###### **Gestion des checkboxs des catégories**
checkCategoriesSelection = new SelectionModel</string>(true);

###### *À remplir*
convertUnicodeFrom2Characters = convertUnicodeFrom2Characters;

###### **Gestion de l'arborescence des catégories**
sources: Map<string, MatTreeFlatDataSource<CategoryNode, CategoryFlatNode>>;

###### **Les contrôles des catégories**
controls: Map<string, FlatTreeControl</CategoryFlatNode>>;

###### *À remplir*
treeFlattener: MatTreeFlattener<CategoryNode, CategoryFlatNode>;

###### **Map from flat node to nested node. This helps us finding the nested node to be modified**
*À traduire*
flatNodeMap = new Map<CategoryFlatNode, CategoryNode>();

###### **Map from nested node to flattened node. This helps us to keep the same object for selection**
*À traduire*
nestedNodeMap = new Map<CategoryNode, CategoryFlatNode>();

###### **La selection pour les checklists**
checklistSelection = new SelectionModel</CategoryFlatNode>( true /* multiple */);

###### **Mapping entre le nom d'un fichier et son statut de chargement**
isFileTreeReady$ = new BehaviorSubject<Map<string, boolean>>(
    new Map<string, boolean>()
);



Constructeur :
- private [[Ifc Service]]
- private DbService
- public LoadingService
- public [[Viewer-facade]]


###### **Initialisation de la liste des catégories 
Pour chaque catégorie un subset est initialisé**
async setupAllCategories(viewerFile: ViewerFile, localFile: boolean)

###### **Creation du subset et sotckage dans le tableau subsets pour le mettre à disposition des checkbox**
async setupCategory(

    categoryKey: string,
    categoryValue: number,
    viewerFile: ViewerFile,
    localFile: boolean,
    tree: CategoryNode
): CategoryNode


###### **Vérifie si le model est séléctionner**
isModelSelected(fileName: string): boolean

###### **Vérifie si une catégorie est séléctionner**
isCategorySelected(category: string): boolean

###### **Checkbox à la racine de l'arbre des catégories d'un fichier**
selectFromRootCheckbox(fileName: string)

###### **Checkbox dans l'arbre des catagories**
selectFromCategoryCheckbox(category: string, fileName: string)

###### **Checkbox dans la liste accessible pour chaque catagories**
async selectFromItemCheckbox(

    categoryName: string,
    itemId: number,
    fileName: string,
    selectionEvent?: boolean
)

###### **Mise en surbrillance d'un item lors du passage de la souris sur sa représentation dans l'arborescence**
preSelectFromCategories(modelId: number, expressID: number)

###### **Gestion de l'arborescence et des sélections**
buildCategoryNode(

    categoryNode: CategoryNode,
    fileName: string,
    categoryKey: string
)

###### **Toggle the to-do item selection. Select/deselect all the descendants node**
*À traduire*
categorySelectionToggle(node: CategoryFlatNode, fileName: string): void

###### **Toggle a leaf to-do item selection. Check all the parents to see if they changed**
*À traduire*
categoryItemSelectionToggle(node: CategoryFlatNode, fileName: string): void

###### **Checks all the parents when a leaf node is selected/unselected**
*À traduire*
checkAllParentsSelection(node: CategoryFlatNode, fileName: string): void

###### **Check root node checked state and change it accordingly**
*À traduire*
checkRootNodeSelection(node: CategoryFlatNode, fileName: string): void

###### **Récupère la node parent**
getParentNode(

    node: CategoryFlatNode,
    fileName: string
): CategoryFlatNode | null

###### **Récupère le niveau de la catégorie**
getLevel = (node: CategoryFlatNode)

###### **Vérifie si la catégorie possède des enfants**
hasChild = ( _ : number, _ nodeData: CategoryFlatNode)

###### **Vérifie si la catégorie peut être étendue**
isExpandable = (node: CategoryFlatNode)

###### **Récupère les enfants de la catégorie**
getChildren = (node: CategoryNode): CategoryNode[]

###### **Transformer to convert nested node to flat node. Record the nodes in maps for later use.**
*À traduire*
transformer = (node: CategoryNode, level: number)
  
###### **Séléctionne tous les déscendants de la catégorie**
descendantsAllSelected(node: CategoryFlatNode, fileName: string): boolean

###### **Séléctionne une partie des déscendants de la catégorie**
descendantsPartiallySelected(

    node: CategoryFlatNode,
    fileName: string
): boolean

###### **Séléctionne une catégories**
pickCategory(expressIds: number[])