Ce composant sert à générer tous les contrôles lié au cube


scene: Scene
width: number
height: number;

camera: OrthographicCamera;
ambientLight: AmbientLight;

renderer: WebGLRenderer;

boxCube: [[BoxCube]];

rayCaster: Raycaster;

Coordonnée de la souris
mouse: Vector2

Indique quand la souris survole le container
mouseOn: boolean

Table de la position de tous les éléments du cube
positionArray: Vector3[]

Le Mesh trouvé
foundMesh: Mesh

Indique si le cube est en pleine animation
cubeInAnimation: boolean



initialise la caméra
initCamera(): OrthographicCamera

initialise les lumières
initLight(): AmbientLight

initialise le renderer
initRenderer(): WebGLRenderer

Initialise le raycaster
initRayCaster(): Raycaster

Traque le mouvement de la souris dans le container
cast(event: MouseEvent): void

Met en place les fonctions onMouseMove et onMouseOut du container du cube
onHover(): void

S'active lorsque la souris bouge dans le container
private handleMove = async (event: MouseEvent)

S'active lorsque la souris sors du container
private handleOut = async ()

Change la couleur de la partie survolé du cube
hover(): void

Repère la partie du cube qui à été cliqué et transmet les résultats à la fonction switchPick contenue dans [[BoxCube]]
onPick(camera: Camera, controls: OrbitControls, ifcCamera: IfcCamera, centroid: Vector3): void

Anime la caméra de sorte à ce quelle pointe dans la même direction que la caméra du viewer
animate(camera: Camera, controls: OrbitControls, centroid: Vector3): void