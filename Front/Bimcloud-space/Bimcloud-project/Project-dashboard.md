Ce composant montre un récapitulatif des détailles du projet.


Le projet
@Input() project: Project;

Nombre de fichiers, membres et topics du projet
nbFiles = 0
nbMembers = 0
nbTopics = 0

Rayon du graphique
GRAP_RADUIS: number[] = [80, 100]

Options de base du graphique
BASE_GRAPH_OPTIONS: EChartsOption = {

    tooltip: {
      trigger: 'item',
      formatter: '{a} <br/>{b} : {c} ({d}%)',
    },
    calculable: true,
    series: [
      {
        name: 'area',
        type: 'pie',
        radius: this.GRAP_RADUIS,
      },
    ],
 }

Options et thème du graphique
priorityOptions: EChartsOption = {}
priorityTheme = { color: ['#ED190C', '#F7C81E', '#40A9E1'] }

Services utilisé :
- [[Ifc Service]]
- [[Topics-service]]
- TranslatePipe


Initialise le dashboard
initDashboard(): void