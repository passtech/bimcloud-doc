Ce service permet de modifier et d'actualiser tous les paramètres de la scène.

Permet de récupérer les paramètres enregistré
settings$: Observable</ISettings>;

Les paramètres utilisé pour enregistré les nouvelles préférences de l'utilisateur
localSettings: ISettings | undefined;

Les paramètres utilisé
parameters: {[key: string]: any}

Les paramétres par défaut
defaultParameters: {[key: string]: any}

Contrôle l'affichage de l'axe dans la scène
axesStatus: boolean

Contrôle l'affichage de la grille dans la scène
gridStatus: boolean

Permet de vérifier si l'utilisateur est connecter
isConnected$: Observable</boolean>;

Table des subscritpions
subscriptions: Subscription[]


Services utilisé :
- SettingsFacade
-  [[Ifc Service]]
- AuthFacade

Change la couleur de l'axe x
changeXColor(debut?: number[], fin?: number[])

Change la couleur de l'axe z
changeZColor(debut?: number[], fin?: number[])

Change la couleur de l'axe y
changeYColor(debut?: number[], fin?: number[])

Change la taille de l'axe
changeAxesLength(length: number)

Met à jour l'axe helper de la scène
renderAxes()

Change les paramètres de la grille
changeGridPreference(

	gridLength?: number, 
	centerLineColor?: THREE.Color, 
	gridColor?: THREE.Color
)

Change la couleur et l'opacité de la présélection
changePreselectionPreference(color?: number, opacity?: number)

Change la couleur et l'opacité de la sélection
changeSelectionPreference(color?: number, opacity?: number)

Change la couleur et l'opacité du surlignage
changeHighlightPreference(color?: number, opacity?: number)

Change la couleur du fond du viewer
changeBackgroundPreference(color: THREE.Color)

Permet de faire un render après avoir charger les nouvelles préférences
renderScene()

Permet de charger toutes les préférences à la création du viewer
loadPreferences(parameters: {[key: string]: any}): void

Récupère les nouvelles préférences et les sauvegardes.
saveParameters(newParameters: {[key: string]: any}): void

Changement de l'état de l'axe
changeStateAxes(): void

Changement de l'état de la grille
changeStateGrid(): void

Créer les MeshMaterial pour la pre-séléction, la séléction et le surlignage
private newMaterial(color: number, opacity: number): MeshLambertMaterial

Récupère les paramètres
getParameters(): {[key: string]: any}

Vérifie que les paramètres sont correctement créer
isWrongParameters(givenParameters: {[key: string]: any}): {[key: string]: any}