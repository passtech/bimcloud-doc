### Ce composant permet de visualiser et réaranger tout les éléments choisis pour constituer le pdf que l'utilisateur veut créer.

###### **Récupère la table des élément pdf choisis depuis le composant [[Reports]]**
@Input() orderElementPdf: Array<{url?: string;name?: string;data?: HTMLTableElement;}>

###### **Emetteur utiliser à la destruction du composant pour communiquer le nouvelle ordre des éléments**
@Output() orderEmitter = new EventEmitter<Array<{url?: string; name?: string; data?: HTMLTableElement;}>>()

###### **Le nom du projet, utilisé pour le pdf**
projectName: string

Constructeur :
- private [[Ifc Service]]
- private [[Topic Service]]
- private [[Topics-service]]

###### **Récupère le screenshot dans ifcService et l'ajoute au tableau**
addScreenshot(): void

###### **Change l'ordre des élements du PDF**
sortElement(index: number, sort: string): void

###### **Supprime un rapport**
deleteElement(index: number): void

###### **Créer le pdf**
createPdf(): void