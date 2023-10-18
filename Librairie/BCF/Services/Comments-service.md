### Permet d'ajouter, de récupérer, de manipuler et de supprimer les [[Comment]]


###### **Supprime un commentaire**
bcfVersionProjectsProjectIdTopicsTopicIdCommentsCommentIdDelete(

	version: string, 
	projectId: string, 
	topicId: string, 
	commentId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</any>


###### **Récupère un commentaire**
public bcfVersionProjectsProjectIdTopicsTopicIdCommentsCommentIdGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	commentId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Comment>

###### **Modifie un commentaire**
public bcfVersionProjectsProjectIdTopicsTopicIdCommentsCommentIdPut(

	body: Comment, 
	version: string, 
	projectId: string, 
	topicId: string, 
	commentId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Comment>

###### **Récupère tous les commentaires appartement au topic**
public bcfVersionProjectsProjectIdTopicsTopicIdCommentsGet(

	version: string, 
	projectId: string, 
	topicId: string, 
	filter?: string, 
	orderby?: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable<Array</Comment>>

###### **Créer un nouveau commentaire**
public bcfVersionProjectsProjectIdTopicsTopicIdCommentsPost(

	body: Comment, 
	version: string, 
	projectId: string, 
	topicId: string, 
	observe?: 'body', 
	reportProgress?: boolean
): Observable</Comment>