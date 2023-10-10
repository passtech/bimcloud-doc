Ce composant permet de visualiser les détailles de chaque type d'élément dans chaque modèles.

Les données récupérer depuis le composant [[Reports]]
@Input() datas: Array<{

    name: string;
    uuid: string;
    lastModDate: any;
    size: number;
    nameOctets: string;
    categories: Array<{
      type: string;
      number: number;
      details: Array<{
        type: string;
        predefinedType?: string;
        number: number;
      }>;
    }>;
    nbMarkers: number;
    isDetails: boolean;
  }>

Détermine si les datas possèdent des détailles
gotDetails: boolean

Génération d'un fichier excel avec sheetjs
generateExcel(data: any)