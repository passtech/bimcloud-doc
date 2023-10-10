Ce composant affiche tous les niveaux de tous les composants et permet d'activer le plan de coupe associé à ce niveau.

Tableau des niveaux
floors: Array<{
	id: number; 
	name: string; 
	type: string; 
	viewerFile?: ViewerFile; 
	labels: Array<{ 
		expressid: string; 
		attr: string; 
		name: string 
	}>; 
}>

Tableau des subscriptions
subscriptions: Subscription[]

Définit si un plan de coupe est actif ou non
isPlanView: boolean

Service utilisé :
- [[Ifc Service]]
- [[Viewer-facade]]
- BimcloudSpaceService
- [[Topic Service]]
- LoadingService

Remplit le tableau des niveaux lors de l'initialisation du composant.
openFloor(): void

Affiche la coupe du model par rapport au niveau choisis.
setLookAtFloor(index: number, expressID: string, name: string, type: string): void

Arrête la coupe du model.
exitPlanView(): void