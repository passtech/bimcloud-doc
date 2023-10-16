Permet d'ajouter, de récupérer, de manipuler et de supprimer les [[Topic]]


Récupère tous les topics
public bcfVersionProjectsProjectIdTopicsGet(

	version: string,
	projectId: string,
	filter?: string,
	orderby?: string,
	top?: string,
	skip?: string,
	observe?: 'body',
	reportProgress?: boolean
): Observable<Array</Topic>>


Créer un nouveau topic
public bcfVersionProjectsProjectIdTopicsPost(

	body: Topic, 
	version: string, 
	projectId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Topic>;

Supprime un topic
public bcfVersionProjectsProjectIdTopicsTopicIdDelete(

	version: string, 
	projectId: string, 
	topicId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</any>

Rcupère un topic
public bcfVersionProjectsProjectIdTopicsTopicIdGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Topic>

Modifie un topic
public bcfVersionProjectsProjectIdTopicsTopicIdPut(

	body: Topic, 
	version: string, 
	projectId: string, 
	topicId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Topic>