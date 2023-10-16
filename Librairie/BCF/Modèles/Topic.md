Le modèle d'un topic

L'index
guid?: string;

L'index du serveur
server_assigend_id?: string;

Le type
topic_type?: string;

Le status
topic_status?: string;

Les liens de références
reference_links?: Array</string>;

Le titre
title: string;

La priorité
priority?: string;


index?: number;

Les labels
labels?: Array</string>;

La date de création
creation_date: string;

L'auteur qui à créer le topic
creation_author: string;

La date de la dernière modification
modified_date?: string;

L'auteur de la dernière modification
modified_author?: string;

À qui il est assigné
assigned_to?: string;

stage?: string;

La description
description?: string;

Le BimSnippet
bim_snippets?: BimSnippet;

La date de rendu
due_date?: string;

Les authorisations
authorization?: TopicAuthorization;

Les [[Comment]]
comments?: [[Comment]][];

Le [[Viewpoint]] (Cette variable n'enregistre et ne recupère aucun information depuis la BDD)
viewpoint?: [[Viewpoint]];

Les [[Viewpoint]]
viewpoints?: [[Viewpoint]][];