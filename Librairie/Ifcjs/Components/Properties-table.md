### Ce composant affiche les propriétés et les propriétés étendues (pset) de l'éléments choisie.



###### **Tableau contenant une propriété**
dataSources: MatTableDataSource</ifcProperty>[]

###### **Table des groupes de propriétés**
propertyGroups: ifcPropertyGroup[]

###### **L'index du model sélectionner**
- selectedModelId$: Observable<number | null | undefined>
- @Input() selectedModelId: number | undefined
###### **L'index de l'item sélectionner**
- selectedItemId$: Observable<number | null | undefined>
- @Input() selectedItemId: number | undefined

###### *À remplir*
@Input() forLocalFiles?: boolean

###### *À remplir*
@Output() currentGlobalId = new EventEmitter</string>()

###### **Renvoie le nom de l'item**
@Output() currentItemName = new EventEmitter</string>()


Constructeur :
- private [[Ifc Service]]
- private [[Viewer-facade]]
- private DbService
- private ChangeDetectorRef
- private ActivateRoute


###### **Vérifie si la valeur est un array**
valueIsArray(value: any): boolean

###### **Vérifie si la valeur est un objet**
valueIsObject(value: any): boolean

###### **Permet de mapper un objet**
mapObject(object: any): any[]

###### **Recharge les données**
reloadPropertiesTable()

###### **Obtenir les propriétés et les mettre à jour quand il y a un double clique sur un item du model ifc**
updateProperties = async (id: number, modelID?: number)

###### **Obtenir les propriétés issues d'un fichier json et les mettre à jour quand il y a un double clique sur un item du model**
updatePropertiesFromIdb = async (

    id: number,
    modelID?: number,
    viewerFile?: ViewerFile
) 

###### **Modifie les propriétés depuis Bim Catalogue**
updatePropertiesFromBimcatalogue = async (

    id: number,
    modelID?: number,
    viewerFile?: ViewerFile
): void

###### **Récupération des propriétés de l'élément sélectionné dans le modèle avec l'API IFC.js**
async getGroupProperties(modelID: number, id: number)

###### **Récupération des propriétés de l'élément sélectionné dans le modèle issues d'un fichier json**
async getGroupPropertiesFromIdb(viewerFile: ViewerFile, id: number)

###### **Trier les propriétés, il y a les propriétés contenu dans la classe IFC, propriétés défini par l'utilisateur et les propriétés définis par le type de l'élément pour un item du model**
async getPropertyGroups(props: any, modelID: number)

###### **Trier les propriétés issues du fichier json, il y a les propriétés contenu dans la classe IFC, propriétés défini par l'utilisateur et les propriétés définis par le type de l'élément pour un item du model**
async getPropertyGroupsFromIdb(props: any, viewerFile: ViewerFile)

###### **Transformation des propriétés en objet clé (nom de la proprité) - valeur à partir des propriétés contenue dans le JSON**
getProps(props: any, isProps?: boolean)

###### **Transformation des propriétés en objet clé (nom de la proprité) - valeur à partir des propriétés contenus dans IndexeDB**
getPropsFromIdb(props: any, isProps?: boolean)

###### **Traitement de l'affichage de la valeur d'une propriété**
getProp(prop: any)