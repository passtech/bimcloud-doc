### Regroupe toutes les actions disponibles du viewer partagées entre les différents composants du viewer.


###### **projet en cours de visualisation**
currentProject$ = this.store.pipe( 
	select(ViewerSelectors.selectCurrentProject) 
);

###### **Vérifie si un chargement est en cours**
isLoading$ = this.store.pipe(
	select(ViewerSelectors.selectFileIsLoading)
);

###### **fichiers en cours chargés dans le viewer**
filesLoaded$ = this.store.pipe(select(ViewerSelectors.selectLoadedFiles));

###### **nombre de fichiers chargés dans le viewer**
totalLoadedFiles$ = this.store.pipe(select(ViewerSelectors.selectTotalLoadedFiles));

###### **nombre de fichiers chargés et ouverts dans le viewer**
totalLoadedAndDisplayedFilesLength$ = this.store.pipe(select(ViewerSelectors.selectTotalLoadedAndDisplayedFilesLength));

###### **les fichiers chargés et ouverts dans le viewer**
totalLoadedAndDisplayedFiles$ = this.store.pipe(select(ViewerSelectors.selectTotalLoadedAndDisplayedFiles));

###### **modèle en cours de traitement par le viewer**
modelId$ = this.store.pipe(select(ViewerSelectors.selectCurrentModelId));

###### **liste des Id des modèles**
modelsIds$ = this.store.pipe(select(ViewerSelectors.selectModelsIds));

###### **Menu**
currentContextMenu$ = this.store.pipe(
    select(ViewerSelectors.selectCurrentContextMenu)
);

###### **Fichier courant dans le viewer**
loadFile$ = this.store.pipe(select(ViewerSelectors.selectCurrentViewerFile));

###### **L'index de l'item séléctionner**
selectedItemId$ = this.store.pipe(
    select(ViewerSelectors.selectSelectedItemId)
);

###### **L'index du model séléctionner**
selectedModelId$ = this.store.pipe(
    select(ViewerSelectors.selectSelectedModelId)
);

###### **Ouvre les propriétés**
openPropertiesTable$ = this.store.pipe(
    select(ViewerSelectors.selectOpenPropertiesTable)
);

###### **Suivi du chargement des modèles**
currentProgress$ = new BehaviorSubject</number>(0);

###### *À remplir*
progressStatus$ = new BehaviorSubject</boolean>(false);

###### *À remplir*
loadModelStatus$ = this.store.pipe(
    select(ViewerSelectors.selectLoadModelStatus)
);

###### *À remplir*
propertiesIndexationInProgress$ = this.store.pipe(
    select(ViewerSelectors.selectPropertiesIndexationInProgress)
);

###### **Suivi de l'affichage du cube component**
cubeStatus$ = this.store.pipe(
    select(ViewerSelectors.changeCubeStatus)
);

###### **Suivi de l'affichage des annotations**
annotationStatus$ = this.store.pipe(
    select(ViewerSelectors.changeAnnotationStatus)
);

###### **Vérifie si l'utilisateur est connécter**
isConnected$ = this.store.pipe(
    select(ViewerSelectors.changeConnectionStatus)
);

constructor :
- private readonly Store
- private NgZone



###### **Chargement des fichiers de la base de données**
loadProject(project: IProject, isPublic: boolean, isLocal: boolean): void

###### **Préparation d'un fichier chargé localement pour la visionneuse locale**
initLocalFile(localFile: File): void

###### **Chargement d'un fichier localement pour la visionneuse en local**
loadLocalFile(localFile: File): void

###### **Supprime un fichier du projet**
removeProjectFile(viewerFile: ViewerFile, projectId: string): void

###### **Ouvre les propriétés**
openPropertiesTable(): void

###### **Ferme les propriétés**
closeProperties(): void

###### **export des fichier de pre calcul (gltf, propriété au format json, indexation des propriétés pour l'arborescence) du fichier ifc**
exportPreprocessingFiles(fileIFC: File, fileName: string, privateFile: boolean, projectId: string, storageProvider: Provider, replace: boolean, exportTree: boolean): void

###### **Exporte le fichier gltf**
exportGLTF(fileIFC: File,fileName: string,privateFile: boolean,projectId: string,storageProvider: string): void

###### **export de l'arborescence au format JSON**
exportSpatialTree(propertiesJSON: File, fileName: string, privateFile: boolean, projectId: string, storageProvider: string): void

###### **Chargement du contenu d'un fichier pour affichage dans le viewer**
loadFile(viewerFile: ViewerFile, forPublicProject: boolean): void

###### **Recharge le model après avoir fermer les catégories**
reloadModelAfterClosingCategories(viewerFile: ViewerFile, isLocal?: boolean, isPublic?: boolean): void

###### **Affichage d'un model déjà chargé précédement**
loadModel(viewerFile: ViewerFile): void

###### *À remplir*
updateLoadModelStatus(status: string, local?: boolean): void

###### *À remplir*
updatePropertiesIndexationStatus(viewerFile: ViewerFile, status: boolean, arePropertiesIndexed: boolean): void

###### **Chargement du fichier de propriétés d'un modèle**
loadProperties(viewerFile: ViewerFile, json: Blob, forTree?: boolean, projectId?: string): void

###### **Chargement des propriétés de l'élément séléctionné**
loadSelectedProperty(
    viewerFile: ViewerFile,
    expressID: number,
    modelID?: number
): void

###### **Fermeture d'un model ouvert dans le viewer**
closeModel(viewerFile: ViewerFile): void

###### **Visualisation d'un fichier dans le viewer ou suppression de la vue si déjà visible**
displayOrUndisplayFile(viewerFile: ViewerFile, asPublicProject: boolean): string

###### *À remplir*
handleContextMenu(contextMenu: ContextMenu): void

###### *À remplir*
resetFileState(): void

###### **Supprime un fichier local**
emoveLocalFile(localFile: File | null | undefined): void

###### **Désactive l'affichage du cube**
disableCube(): void

###### **Désactive l'affichage des annotations**
disableAnnotation(): void

###### **Retourne le nombre de fichiers charger**
getTotalFilesLoaded(): number

###### **Retourne le nombre de fichiers affiché dans la scène**
getTotalDisplayedFiles(): number

###### *À remplir*
changeModelIndex(index: number)