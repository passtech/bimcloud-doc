Ce composant permet de modifier le nom, la description et le type de stockage du projet.


Variable du formulaire
name = new FormControl</string>('', Validators.required);
description = new FormControl</string>('');
projectStorageProvider = new FormControl</Provider>(null);

Spécification du formulaire
formGroup = this._formBuilder.group({

    name: this.name,
    description: this.description,
    storageProvider: this.projectStorageProvider,
});

Le projet
@Input() project: Project;

private unsubscribe = new Subject</void>();

Selecteur de fournisseur de service
readonly providerIconsMap = new Map<Provider, IconDefinition>([

    [Provider.DROPBOX_STORAGE, faDropbox],
    [Provider.GOOGLE_DRIVE_STORAGE, faGoogleDrive],
    [Provider.ONEDRIVE_STORAGE, faMicrosoft],
    [Provider.AMAZON_S3_STORAGE, faAmazon],
    [Provider.AUTODESK_OAUTH, faHome],
    [Provider.LOCALHOST_STORAGE, faServer],
    [Provider.SFTP_STORAGE, faServer],
    [Provider.FTPS_STORAGE, faServer],
 ]);

Selecteur de fournisseur de service
readonly providerTextMap = new Map<Provider, string>([

    // [Provider.DROPBOX_STORAGE, 'global.providers.dropbox'],
    [Provider.GOOGLE_DRIVE_STORAGE, 'global.providers.google-drive'],
    // [Provider.ONEDRIVE_STORAGE, 'global.providers.onedrive'],
    // [Provider.AMAZON_S3_STORAGE, 'global.providers.amazon-s3'],
    // [Provider.AUTODESK_OAUTH, 'global.providers.autodesk'],
    [Provider.LOCALHOST_STORAGE, "global.providers.local-storage"],
    // [Provider.SFTP_STORAGE, 'global.providers.sftp'],
    // [Provider.FTPS_STORAGE, 'global.providers.ftps'],
]);



Service utilisé :
- UserService
- BimcloudSpaceService
- MatDialog
- FormBuilder




changeProjectStorageProvider(newProviderInUse: Provider)

Sauvegarde les nouvelles informations du projet
save()

Ouvre un MatDialog pour importer un nouveau logo pour le projet
importLogo()