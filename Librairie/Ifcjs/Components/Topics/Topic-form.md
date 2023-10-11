Ce composant est un formulaire permettant de créer des topics dans le projet

Valeur de base du choix de la forme du topic
selectBaseShape = 'cone';

Valeur de base de la couleur du topic
inputBaseColor = '#4E7FD4';

Valeur de base de la priorité du topic
selectBasePriority = 'No-priority';

Valeur de base du status du topic
selectBaseStatus = 'No-status';

Valeur de base du type du topic
selectBaseType = 'No-type';

Valeur du screenshot du viewpoint associé au topic
viewpointScreenshot: string

Récupère le nom de l'auteur
author: string

Permet d'afficher les textes d'érreur si les éléments obligatoire ne sont pas renseigner
- markerFormRedText: boolean
- titleRedText: boolean
- markerProjectionRedText: boolean

Contrôle l'apparition de la projection du topic sur le modèle
isProjected = false;

Table des subscriptions
subscription: Subscription[]

Services utilisé:
- AuthFacade,
- [[Ifc Service]]
- [[Topic Service]]
- ChangeDetectorRef
- [[Topics-service]]
- [[Viewpoints-service]]


Change la forme de la projection et du topic
changeForm(form: NgForm): void

Change le status de la projection
changeProjectionState(bool: boolean): void

Permet de créer un nouveau topic (la manière diffère si le viewer est le viewer local ou un viewer privé/publique)
createNewTopic(form: NgForm): void

Récupère le screenshot de la scène
getScreenshot(): void

Supprime le screenshot stocké
deleteScreenshot(): void

Permet de créer le viewpoint pour le topic
getViewpoint(

    form: string,
    color: string,
    title: string,
    projectName?: string,
    date?: Date
): Viewpoint | undefined

Ferme le formulaire sans créer le topic
cancelNewTopic(): void