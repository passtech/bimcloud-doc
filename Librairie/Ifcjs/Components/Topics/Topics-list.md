Ce composant permet de lister tous les topics présent dans le projet.
Ce composant permet aussi de créer un nouveau topic en ouvrant le composant [[Topic-form]] ou d'afficher les informations complet d'un topic en ouvrant le composant [[Topic-viewer]]

Contrôle l'affichage complet d'un topic
isVisualize: boolean

Contrôle l'affichage du formulaire de création d'un topic
isForm: boolean

La langue actuelle utilisé pour les dates.
currentLang: string
  
Stockage des topics du projet
localTopics: Topic[]

Stockage du topic choisis par l'utilisateur
localTopic: Topic | undefined

Index reçu depuis [[Project-viewer]] permettant de passer directement à l'affichage complet du topic choisis
@Input() localTopicId: string | undefined

Emetteur indiquant au [[Project-viewer]] de réinitialisé le localTopicId
@Output() closedTopicEmitter = new EventEmitter()

Indique le type de filtre à utiliser
filterMode: number

Table de subscriptions
subscriptions: Subscription[]

Contrôle l'apparition du texte qui indique que le projet ne possède aucun topics
showNoTopicsText: boolean

L'index du projet
projectId: string

Services utilisé:
- [[Ifc Service]]
- [[Viewer-facade]]
- [[Topic Service]]
- LangFacade
- ChangeDetectorRef
- [[Topics-service]]
- LoadingService


Permet de récupérer les topics (la manière diffère si le viewer est le viewer local ou un viewer privé/publique)
getTopics(): void

Lance l'affichage complet du topic choisis
startVisualize(topic: Topic, id: string): void

Lance l'affichage du formulaire de création d'un nouveau topic
beginNewTopic(): void

Ferme l'affichage du formulaire
closeFormEmit(e: boolean): void

Ferme l'affichage complet du topic
closeViewerEmit(e: boolean): void

Change le mode de filtrage
changeFilterMode(mode: number): void