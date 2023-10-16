### Ce composant permet de modifier et enregistrer les préférences de la scène.


###### **Contrôle de l'affichage du cube.**
cubeStatus: boolean

###### **Contrôle de l'affichage des annotations au survol des boutons dans le project-viewer.**
annotationStatus: boolean

###### **Contrôle de la langue utilisé par l'utilisateur.**
langueStatus: string

###### **Stocke les paramètres déjà enregistrer dans PreferenceService**
parameters: { [key: string] : any}

###### **Stockage des models chargé dans le viewer.**
models: {key: string, modelID: number, object: THREE.Object3D}[]

###### **Stockage des subscriptions.**
subscriptions: Subscription[]

###### **Définit la valeur de base de la lumière ambiente**
inputBaseValue = 0.25


Constructeur :
- private [[Ifc Service]]
- private LangFacade
- private [[Preferences Service]]
- private AuthFacade
- private [[Topic Service]]
- private ChangeDetectionRef
- private [[Viewer-facade]]


###### **Change la couleur d'un axe dépendant de l'input choisie.**
changeAxesColor(elementId: string): void

###### **Change la couleur de la grille**
changeGridColor(): void

###### **Change la couleur de la ligne centrale de la grille**
changeCenterLineColor(): void

###### **Change la taille de l'axe**
changeAxesLength(): void

###### **Change la taille de la grille**
changeGridLength(): void

###### **Change la couleur de la pré-sélection**
changePreselectionColor(): void

###### **Change la couleur de la sélection**
changeSelectionColor(): void

###### **Change la couleur du surlignage**
changeHighlightColor(): void

###### **Change l'opacité de la pré-sélection**
changePreselectionOpacity(): void

###### **Change l'opacité de la sélection**
changeSelectionOpacity(): void

###### **Change l'opacité du surlignage**
changeHighlightOpacity(): void

###### **Change la couleur du fond de la scène**
changeBackgroundColor(): void

###### **Remet toutes les valeurs par défaut de la scène**
reset(): void

###### **Défini si le cube est affiché ou non**
changeCubeStatus(): void

###### **Défini si les annotations sont affiché ou non**
changeAnnotationStatus(): void

###### **Change la langue actuellement utilisé**
changeLang(): void

###### **Calcul la couleur hexadécimale des axes à partir d'un tableau de 3 nombres**
calculAxisParameters(param: number[] ): string

###### **Calcul la couleur hexadécimale des autres inputs à partir d'un nombre**
calculColor(param: number): string

###### **Permet de stocker les models présent dans le viewer**
stockModels(): void

###### **Pousse le model choisie sur l'axe X**
pushOnX(index: number): void

###### **Pousse le model choisie sur l'axe Y**
pushOnY(index: number): void

###### **Pousse le model choisie sur l'axe Z**
pushOnZ(index: number): void

###### **Tourne le model choisie sur l'axe X**
rotateOnX(index: number): void

###### **Tourne le model choisie sur l'axe Y**
rotateOnY(index: number): void

###### **Tourne le model choisie sur l'axe Z**
rotateOnZ(index: number): void

###### **Change l'intensité de la lumière ambiante**
changeLightIntensity(): void