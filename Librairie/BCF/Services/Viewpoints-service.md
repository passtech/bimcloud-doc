Permet d'ajouter, de récupérer, de manipuler et de supprimer les [[Viewpoint]]


Récupère tous les viewpoints
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable<Array</Viewpoint>>

Créer un viewpoint
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsPost(

	body: Viewpoint, 
	version: string, 
	projectId: string, 
	topicId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Viewpoint>

Récupérer les bitmaps d'un viewpoint
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsViewpointIdBitmapsBitmapIdGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	viewpointId: string, 
	bitmapId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Blob>;

Récupère les composents coloriés
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsViewpointIdColoringGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	viewpointId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable<Coloring[]>

Supprime un viewpoint
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsViewpointIdDelete(

	version: string, 
	projectId: string, 
	topicId: string, 
	viewpointId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</any>

Récupère un viewpoint
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsViewpointIdGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	viewpointId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Viewpoint>

Récupère les composents séléctionnés
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsViewpointIdSelectionGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	viewpointId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</ComponentList>

Récupère le [[Snapshot]] d'un viewpoint
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsViewpointIdSnapshotGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	viewpointId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Blob>

Récupère la visibilité des composants
public bcfVersionProjectsProjectIdTopicsTopicIdViewpointsViewpointIdVisibilityGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	viewpointId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Visibility>