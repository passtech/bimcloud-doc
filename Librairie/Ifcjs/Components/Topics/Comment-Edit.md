### Ce composant permet d'éditer le commentaire choisis par l'utilisateur


###### **Le topic choisis**
@Input() localTopic: Topic | undefined;

###### **Le commentaire choisis**
@Input() localComment: Comment | undefined;

###### **L'index du commentaire**
@Input() localCommentId: number | undefined;

###### **Émetteur communiquant la fin de l'édition**
@Output() closeEmitter = new EventEmitter</boolean>();

###### **Émetteur communiquant l'annulation de l'édition**
@Output() cancelEmitter = new EventEmitter</Comment>();

###### **Le commentaire de base en cas d'annulation de l'édition.**
baseComment: Comment | undefined;

###### **Le viewpoint de base en cas d'annulation**
baseViewpoint: Viewpoint | undefined;

###### **Le nouveau viewpoint**
localViewpoint: Viewpoint | undefined;

###### **S'enclenche si le titre n'est pas renseigner.**
contentRedText = false;

###### **Le language actuellement utilisé par l'utilisateur**
currentLang = '';

###### **Table des subscriptions**
subscription: Subscription[]


Services utilisé :
- private LangFacade
- private [[Viewpoints-service]]
- private [[Comment-Edit]]
- private [[Ifc Service]]
- private ChangeDetectorRef
- private [[Topic Service]]


###### **Récupére le bouton de soumission du formulaire et simule un clique dessus**
confirmCommentEdit(): void

###### **Créer un nouveau viewpoint**
createCommentViewpoint()

###### **Supprime le viewpoint**
deleteCommentViewpoint()

###### **Termine l'édition du commentaire et l'enregistre dans la base de données**
*(Se code ne marche que si le viewer est un viewer provenant d'un projet publique/privé)*
createEditComment()

###### **Annule l'édition du commentaire et renvois le commentaire de base**
cancelEditTopic()