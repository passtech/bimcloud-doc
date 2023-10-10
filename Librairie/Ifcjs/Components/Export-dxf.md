Ce composant permet de télécharger le fichier dxf d'un niveau du model choisi

Stockage des plans des models
allViewPlans: Array<{

    id: number;
    key: string;
    type: string;
    allPlans: Array<{ name: string; plan: string }>;
  }>

Tableau des subscritpions
subscriptions: Subscription[]

Service utilisé :
- [[Ifc Service]]
- BimcloudSpaceService
- [[Topic Service]]
- LoadingService

Récupère tous les plans de tous les models chargé dans le viewer
getAllPlans(): void

Créer les informations essentielle à la création du fichier DXF
startExport(

	modelID: number,
    plan: string,
    key: string,
    name: string,
    type: string
): void

Créer le fichier DXF
drawProjectedItems(

    storey: any,
    plan: PlanView,
    modelID: number,
    key: string,
    name: string
  ): void