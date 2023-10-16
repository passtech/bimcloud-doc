Le modèle d'un commentaire

L'index
guid?: string;

La date
date?: string;

L'auteur
author?: string;

Le commentaire
comment: string;

La priorité
priority: string;

L'index du topic à qui il est lié
topic_guid?: string;

L'index du viewpoint qui est lié au commentaire
viewpoint_guid?: string;

L'index du Commentaire à qui il répond
reply_to_comment_guid?: string;

La date de la modification
modified_date?: string;

L'auteur de la modification
modified_author?: string;

Les autorisations
authorization?: CommentAuthorization;

Le viewpoint (Cette variable n'enregistre et ne recupère aucun information depuis la BDD)
viewpoint?: [[Viewpoint]];