## <a name="integration-models-for-solution-providers"></a>Modèles d’intégration pour les fournisseurs de solutions

<a name="steps"></a>

En tant que fournisseur de solutions de centre de contacts, vous avez le choix entre trois modèles pour intégrer votre solution de centre de contacts connecté dans Teams :

- Si vous souhaitez utiliser des SBCs certifiés et un routage direct pour connecter une solution de centre de contacts à Teams, consultez le [Connecter produit.](?tabs=connect#steps)

- Si vous voulez utiliser les robots Azure et les API de communication microsoft Graph pour permettre aux fournisseurs de solutions de créer des applications Teams, voir [le modèle Étendre.](?tabs=extend#steps)

- Si vous voulez utiliser un SDK qui permet aux fournisseurs de solutions d’imbed des expériences natives Teams dans leur application, consultez [le modèle Power.](?tabs=power#steps) Les solutions Power Seront possibles lorsque le SDK sera disponible, vers la fin de l’année 2021.

### <a name="the-connect-model"></a>[**Modèle Connecter modèle de base**](#tab/connect)

Le modèle Connecter utilise des SBCs certifiés Microsoft et un routage direct pour connecter des solutions de centre de contacts à l’infrastructure du système téléphonique Teams, ce qui permet d’améliorer le routage, la configuration et les informations système.

Les agents peuvent configurer des assistants virtuels automatisés et des files d’attente de routage basées sur les compétences pour recueillir des informations et connecter les clients avec des experts techniques.

**Principales caractéristiques de la fonctionnalité :**

Bien que ces fonctionnalités ne sont pas une liste exhaustive des fonctionnalités de ce modèle d’intégration, les domaines clés sont les suivants :

  - Office 365 authN pour que les agents se connectent à leur client Microsoft à partir de leur client CCaaS intégré 

  - Voir si des agents sont disponibles avec Teams

  - Transferts et appel de groupe avec l’Teams 

  - Teams Graph API et API de communication cloud pour l’intégration avec Teams 

  - Ligne SIP multi-client pour prendre en charge plusieurs clients sur le SBC du fournisseur de solutions.  

  - Fournisseurs de solutions pour utiliser le contrôleur de bordure de session certifié [ <span class="underline">Microsoft (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**Modèle Étendre**](#tab/extend)

Le modèle Étendre s’intègre au client Teams à l’aide de la plateforme [cliente Teams,](/microsoftteams/platform/overview)des [API](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) Teams Graph et de l’API de communication cloud dans [Microsoft Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) Le modèle Étendre utilise également le système téléphonique Teams pour tous les appels au centre de contacts et les expériences de contrôle d’appel, et le fournisseur de solutions du centre de contacts agit en tant qu’opérateur téléphonique en parallèle de Microsoft 365.

Les agents peuvent utiliser des Teams pour la collaboration interne et la communication externe, et peuvent tirer avantage de notes dynamiques contextuelles en rapport avec les données de plusieurs systèmes avant de commencer un engagement, et ainsi éviter un changement de contexte coûteux.

Les organisations peuvent concevoir des flux de travail et des configurations de routage avancées jusqu’à la personne et mesurer la qualité de leur système et de leurs interactions.

**Principales caractéristiques de la fonctionnalité :**

Bien que ces fonctionnalités ne sont pas une liste exhaustive des fonctionnalités de ce modèle d’intégration, les domaines clés sont les suivants :

  - Teams Graph API et API de communication cloud pour l’intégration avec Teams 

  - Teams’application basée sur l’agent pour les expériences de l’agent 

  - Teams comme point de terminaison d’appel principal pour les agents 

  - Teams client pour tous les contrôles d’appel

  - Application Expérience de l’agent pour Teams client web et mobile

  - Analyse, gestion des flux de travail, expériences basées sur les rôles pour les agents dans l’application CCaaS dans Teams

  - Les expériences de conversation et de collaboration intégrées Teams clients 

  - Préserver les performances et la qualité des Teams client dans toutes les applications  

### <a name="the-power-model"></a>[**Modèle de puissance**](#tab/power)

Le modèle Power permet aux fournisseurs de solutions de créer des applications vocales Azure natives à l’aide de l’infrastructure d’appels Teams et de la plateforme cliente pour offrir des solutions modernes et intelligentes pour une connexion collaborative entre les clients et les agents. L’objectif du modèle Power est de fournir une expérience de centre de contacts à écran unique.

**Principales caractéristiques de la fonctionnalité :**

Bien que ces fonctionnalités ne sont pas une liste exhaustive des fonctionnalités de ce modèle d’intégration, les domaines clés sont les suivants :

  - Expériences formelles de l’agent activées en natif pour la communication via un canal Teams SDK 

  - Utiliser les services Teams collaboration avec les agents pour la collaboration avec les agents et les interactions avec les clients  

  - Approvisionnement rapide des services cloud, déploiement en tout lieu 

  - Direct conversation control and interaction with users during Teams conversations 

>[!NOTE]
> Le modèle power sera disponible vers la fin de l’année 2021.
