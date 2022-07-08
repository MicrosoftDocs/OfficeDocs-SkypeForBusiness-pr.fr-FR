## <a name="integration-models-for-solution-providers"></a>Modèles d’intégration pour les fournisseurs de solutions

<a name="steps"></a>

En tant que fournisseur de solutions de centre de contacts, vous avez le choix entre trois modèles pour intégrer votre solution de centre de contacts connecté à Teams :

- Si vous souhaitez utiliser des SBC certifiés et le routage direct pour connecter une solution de centre de contacts à Teams, consultez le [modèle Connect](?tabs=connect#steps).

- Si vous souhaitez utiliser des bots Azure et les API de communication Microsoft Graph pour permettre aux fournisseurs de solutions de créer des applications Teams, consultez le [modèle Étendre](?tabs=extend#steps).

- Si vous souhaitez utiliser un Kit de développement logiciel (SDK) qui permet aux fournisseurs de solutions d’imbinger des expériences Teams natives dans leur application, consultez le [modèle Power](?tabs=power#steps). Les solutions d’alimentation sont possibles lorsque le Kit de développement logiciel (SDK) est disponible. À venir.

### <a name="the-connect-model"></a>[**Le modèle Connect**](#tab/connect)

Le modèle Connect utilise des SBC certifiés Microsoft et le routage direct pour connecter des solutions de centre de contacts à l’infrastructure du système téléphonique Teams, ce qui permet un routage, une configuration et des insights système améliorés.

Les agents peuvent configurer des assistants virtuels automatisés et des files d’attente de routage basées sur les compétences pour collecter des informations et connecter les clients à des experts en la matière.

**Points forts des fonctionnalités :**

Bien que ces fonctionnalités ne soient pas une liste complète des fonctionnalités de ce modèle d’intégration, les domaines d’intérêt sont les suivants :

- Office 365 authN pour que les agents se connectent à leur locataire Microsoft à partir de leur client CCaaS intégré

- Voir quand les agents sont disponibles avec Teams

- Transferts et prise en charge des appels de groupe avec Teams

- API Graph Teams et API de communication cloud pour l’intégration à Teams

- Jonction SIP multilocataire pour prendre en charge plusieurs clients sur le SBC du fournisseur de solutions.

- Fournisseurs de solutions pour utiliser le [<span class="underline">contrôleur de frontière de session certifié Microsoft (SBC)</span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**Modèle d’extension**](#tab/extend)

Le modèle Extend s’intègre au client Teams à l’aide de la [plateforme cliente Teams](/microsoftteams/platform/overview), [des API Teams Graph et de](/graph/api/resources/teams-api-overview) [l’API de communications cloud dans Microsoft Graph](/graph/api/resources/communications-api-overview). Le modèle Extend utilise également le système téléphonique Teams pour tous les appels de centre de contacts et les expériences de contrôle des appels, et le fournisseur de solutions de centre de contacts agit comme opérateur téléphonique avec Microsoft 365.

Les agents peuvent utiliser Teams pour la collaboration interne et la communication externe et peuvent tirer parti de notes contextuelles dynamiques qui corrélent des données à partir de plusieurs systèmes avant de démarrer un engagement, puis d’éviter un basculement de contexte coûteux.

Les organisations peuvent concevoir des workflows et des configurations de routage avancées vers l’individu et mesurer la qualité de leur système et de leurs interactions.

**Points forts des fonctionnalités :**

Bien que ces fonctionnalités ne soient pas une liste complète des fonctionnalités de ce modèle d’intégration, les domaines d’intérêt sont les suivants :

- API Graph Teams et API de communication cloud pour l’intégration à Teams

- Application basée sur Teams pour les expériences d’agent

- Teams comme point de terminaison d’appel principal pour les agents

- Client Teams appelant tous les contrôles d’appel

- Application d’expérience d’agent pour le client web et le client mobile Teams

- Analytique, gestion des flux de travail, expériences basées sur des rôles pour les agents dans l’application CCaaS dans Teams

- Expériences de conversation et de collaboration intégrées aux clients Teams

- Préserver les performances et la qualité des expériences client Teams dans toutes les applications

> [!NOTE]
> Le bot agent n’a pas besoin d’une licence de système téléphonique. L’utilisateur Teams a besoin d’une licence de système téléphonique et d’un numéro de téléphone.

### <a name="the-power-model"></a>[**Modèle Power**](#tab/power)

Le modèle Power permet aux fournisseurs de solutions de créer des applications vocales basées sur Azure natives à l’aide de l’infrastructure d’appel teams et de la plateforme cliente pour fournir des solutions modernes et intelligentes pour la connexion collaborative des clients et des agents. L’objectif du modèle Power est de fournir une expérience de centre de contacts à une application et à un écran.


> [!NOTE]
> À venir.
