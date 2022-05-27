## <a name="integration-models-for-solution-providers"></a>Modèles d’intégration pour les fournisseurs de solutions

<a name="steps"></a>

En tant que fournisseur de solutions de centre de contacts, vous avez le choix entre trois modèles pour intégrer votre solution de centre de contacts connectée dans Teams :

- Si vous souhaitez utiliser des SBC certifiés et le routage direct pour connecter une solution de centre de contacts à Teams, consultez le [modèle Connecter](?tabs=connect#steps).

- Si vous souhaitez utiliser des bots Azure et les API Microsoft Graph Communication pour permettre aux fournisseurs de solutions de créer des applications Teams, consultez le [modèle Étendre](?tabs=extend#steps).

- Si vous souhaitez utiliser un Kit de développement logiciel (SDK) qui permet aux fournisseurs de solutions d’imbinger des expériences natives Teams dans leur application, consultez le [modèle Power](?tabs=power#steps). Les solutions d’alimentation seront possibles lorsque le Kit de développement logiciel (SDK) sera disponible, vers la fin de 2021.

### <a name="the-connect-model"></a>[**Modèle Connecter**](#tab/connect)

Le modèle Connecter utilise des SBC certifiés Microsoft et le routage direct pour connecter des solutions de centre de contacts à Teams infrastructure du système téléphonique, ce qui permet un routage, une configuration et des insights système améliorés.

Les agents peuvent configurer des assistants virtuels automatisés et des files d’attente de routage basées sur les compétences pour collecter des informations et connecter les clients à des experts en la matière.

**Points forts des fonctionnalités :**

Bien que ces fonctionnalités ne soient pas une liste complète des fonctionnalités de ce modèle d’intégration, les domaines d’intérêt sont les suivants :

- Office 365 authN pour que les agents se connectent à leur locataire Microsoft à partir de leur client CCaaS intégré

- Voir quand les agents sont disponibles avec Teams

- Transferts et prise en charge des appels de groupe avec Teams

- TEAMS GRAPH API et API de communication cloud pour l’intégration à Teams

- Jonction SIP multilocataire pour prendre en charge plusieurs clients sur le SBC du fournisseur de solutions.

- Fournisseurs de solutions pour utiliser le [<span class="underline">contrôleur de frontière de session certifié Microsoft (SBC)</span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**Modèle d’extension**](#tab/extend)

Le modèle Extend s’intègre au client Teams à l’aide de la [plateforme cliente Teams](/microsoftteams/platform/overview), [des API Teams Graph et de](/graph/api/resources/teams-api-overview) [l’API De communications cloud dans Microsoft Graph](/graph/api/resources/communications-api-overview). Le modèle Extend utilise également le système téléphonique Teams pour tous les appels de centre de contacts et les expériences de contrôle des appels, et le fournisseur de solutions de centre de contacts joue le rôle d’opérateur téléphonique en même temps que Microsoft 365.

Les agents peuvent utiliser Teams pour la collaboration interne et la communication externe et peuvent tirer parti de notes contextuelles dynamiques qui corrélent les données de plusieurs systèmes avant de démarrer un engagement, puis d’éviter un basculement de contexte coûteux.

Les organisations peuvent concevoir des workflows et des configurations de routage avancées vers l’individu et mesurer la qualité de leur système et de leurs interactions.

**Points forts des fonctionnalités :**

Bien que ces fonctionnalités ne soient pas une liste complète des fonctionnalités de ce modèle d’intégration, les domaines d’intérêt sont les suivants :

- TEAMS GRAPH API et API de communication cloud pour l’intégration à Teams

- application basée sur Teams pour les expériences d’agent

- Teams comme point de terminaison d’appel principal pour les agents

- Teams client appelant tous les contrôles d’appel

- Application d’expérience d’agent pour Teams client web et mobile

- Analytique, gestion des flux de travail, expériences basées sur des rôles pour les agents dans l’application CCaaS dans Teams

- Expériences de conversation et de collaboration intégrées aux clients Teams

- Préserver les performances et la qualité des expériences clientes Teams dans toutes les applications

### <a name="the-power-model"></a>[**Modèle Power**](#tab/power)

Le modèle Power permet aux fournisseurs de solutions de créer des applications vocales basées sur Azure natives à l’aide de l’infrastructure d’appel Teams et de la plateforme cliente pour fournir des solutions modernes et intelligentes pour la connexion collaborative entre les clients et les agents. L’objectif du modèle Power est de fournir une expérience de centre de contacts à une application et à un écran.

**Points forts des fonctionnalités :**

Bien que ces fonctionnalités ne soient pas une liste complète des fonctionnalités de ce modèle d’intégration, les domaines d’intérêt sont les suivants :

- Expériences d’agent formel activées en mode natif pour la communication omnicanal via Teams SDK

- Utiliser Teams services de collaboration pour la collaboration des agents et les interactions avec les clients

- Approvisionnement rapide des services cloud, déployer n’importe où

- Contrôle de conversation direct et interaction avec les utilisateurs pendant les conversations Teams

> [!NOTE]
> Le modèle Power sera disponible fin 2021.
