Ce composant affiche les informations complète du topic choisis en plus de pouvoir y ajouter des commentaire.
De plus, il est possible d'éditer le topic via le composant [[Topic-Edit]] ou un des commentaires via le composant [[Comment-Edit]]

L'index du topic choisis
@Input() localTopicId: string | undefined;

Le topic choisis
@Input() localTopic: Topic | undefined;

Emetteur permettant de fermer le composant
@Output() closeEmitter = new EventEmitter</boolean>();

  
Le viewpoint du topic
localViewpoint: Viewpoint | undefined;

Le commentaire chosis pour le composant [[Comment-Edit]]
localComment: Comment | undefined;

L'index du commentaire choisis
localCommentId: number | undefined;

  

Variable boolean permettant d'activer l'édition du topic.
- isEdit = false;
- isEditComment: number | undefined = undefined;

Contrôle l'affichage de l'image du viewpoint
showImage = false;

Variable boolean qui affiche l'espace commentaire.
isComment = false;

Variable boolean qui indique si le topic à été supprimer.
isDeleted = false;

Récupère le nom de l'auteur.
author = '';

La langue actuelle utilisé pour les dates.
currentLang = '';

Permet d'enregistrer les screenshots pour les commentaires.
commentViewpoint: Viewpoint | undefined = undefined;

Table des subscritpions
subscriptions: Subscription[]


Services utilisé :
- [[Topic Service]]
- [[Ifc Service]]
- AuthFacade
- LangFacade
- ChangeDetectorRef
- [[Topics-service]]
- [[Viewpoints-service]]
- [[Comments-service]]
- LoadingService

Récupère toutes les informations du topics
getTopicInformation(): void

Ferme le composant
closeEmit(): void

Active l'édition du topic
startTopicEdit(): void

Active l'édition du commentaire
startCommentEdit(commentId: number): void

Termine l'édition du topic et recharge le viewpoint
finishTopicEdit(e: boolean): void

Termine l'édition du commentaire
finishCommentEdit(): void

Arrète l'édition et restaure le topic
cancelTopicEdit(e: Topic): void

Arrète l'édition et restaure le commentaire
cancelCommentEdit(e: Comment): void

Permet de supprimer le topic (la manière diffère si le viewer est le viewer local ou un viewer privé/publique)
deleteTopic(): void

Permet de supprimer un commentaire (la manière diffère si le viewer est le viewer local ou un viewer privé/publique)
deleteComment(comment: Comment, commentId: number): void

Permet d'afficher ou non le formulaire de création d'un commentaire
changeStateComment(): void

Créer un viewpoint pour la création d'un commentaire
createViewpoint(): Viewpoint | undefined

Génère le viewpoint du commentaire et donne la valeur à commentViewpoint
getCommentViewpoint(): void

Permet de créer et d'enregistrer un nouveau viewpoint pour le topic si le topic ne possède pas de viewpoint
getTopicViewpoint(): void

Supprime le viewpoint du commentaire qui est en cours de création
deleteScreenshot(): void

Supprime le viewpoint du topic si le topic possède un viewpoint
deleteTopicScreenshot(): void

Permet de créer un nouveau commentaire pour le topic
createNewComment(form: NgForm): void

Déplace et tourne la caméra à l'endroit ou le screenshot à été pris
moveCameraToImage(viewpoint: Viewpoint): void