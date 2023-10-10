Ce composant permet de visualiser les annotations créer dans le projet depuis les rapports.
On peut aussi se rendre dans le composant des topics en appuyant sur le badge des commentaires.

Table des topics du projet
@Input() localTopics: Topic[];

Table des éléments pdf choisis
@Input() orderElementPdf: Array<{

    url?: string;
    name?: string;
    data?: HTMLTableElement;
}>

Emetteur qui renvoit la table des éléments pdf choisis à [[Reports]]
@Output() saveEmitter = new EventEmitter<{

      url?: string;
      name?: string;
      data?: HTMLTableElement;
  }[]>();

Emetteur qui indique à [[Reports]] de rediriger l'utilisateur vers les topics
@Output() redirectEmitter = new EventEmitter</string>();

Services utilisé :
- TranslatePipe

Sauvegarde le topic choisis dans la table des élément pdf
saveToPDF(): void

Redirige vers le topic choisis
goToTopic(topicId: string): void