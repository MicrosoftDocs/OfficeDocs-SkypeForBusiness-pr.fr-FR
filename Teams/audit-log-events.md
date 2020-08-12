---
title: Rechercher des événements Microsoft Teams dans le journal d'audit
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
description: Découvrez comment récupérer les données de Microsoft teams à partir du journal d’audit.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64b2e2f28b33a3f0518dbf4f2f07a4be3053d342
ms.sourcegitcommit: 3814db70796888f15ea47d7810e1621a92992870
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "46634610"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Rechercher des événements Microsoft Teams dans le journal d'audit

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Le journal d’audit peut vous aider à rechercher des activités spécifiques dans les services Microsoft 365. Dans Microsoft Teams, voici quelques-unes des activités qui sont auditées :

- Création d'une équipe
- Suppression d'une équipe
- Ajout d'un canal
- Modification d'un paramètre

Pour obtenir la liste complète des activités d’équipe auditées, voir [activités](#teams-activities) et équipes d’équipes [dans les activités d’équipe (en version préliminaire)](#shifts-in-teams-activities).

> [!NOTE]
> Les événements d’audit provenant de canaux privés sont également enregistrés tels qu’ils sont destinés aux canaux des équipes et des canaux standard.

## <a name="turn-on-auditing-in-teams"></a>Activer l’audit dans Teams

Pour pouvoir voir les données d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com). Pour obtenir de l’aide sur l’activation de l’audit, voir [activer ou désactiver la recherche dans le journal d’audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Récupérer des données Teams à partir du journal d'audit

1. Pour récupérer les journaux d’audit, accédez au [Centre de sécurité et de conformité](https://go.microsoft.com/fwlink/?linkid=855775). Sous **Rechercher**, sélectionnez **Rechercher dans le journal d’audit**.
2. Utilisez l’option **Rechercher** pour filtrer les données en fonction des activités, dates et utilisateurs que vous souhaitez vérifier.
3. Pour une analyse plus approfondie, exportez les résultats dans Excel.

> [!IMPORTANT]
> Les données d’audit sont uniquement visibles dans le journal d’audit si l’audit est activé.

La durée de conservation d’un enregistrement d’audit et de la recherche dans le journal d’audit dépend de votre abonnement Microsoft 365 ou Office 365 et en particulier du type de licence attribué aux utilisateurs. Pour en savoir plus, consultez la [Description du service Centre de sécurité & conformité](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Conseils pour la recherche dans le journal d’audit

Vous trouverez ci-dessous des conseils pour rechercher des activités d’équipe dans le journal d’audit.

![Capture d’écran de la page de recherche du journal d’audit](media/audit-log-search-page.png)

- Vous pouvez sélectionner des activités spécifiques à rechercher en cliquant sur le nom de l’activité. Vous pouvez aussi rechercher toutes les activités d’un groupe (par exemple, les **activités des fichiers et des dossiers**) en cliquant sur le nom du groupe. Si une activité est sélectionnée, vous pouvez cliquer dessus pour annuler la sélection. Vous pouvez également utiliser la zone de recherche pour afficher les activités qui contiennent le mot clé que vous tapez.<br>
    ![Capture d’écran de la recherche dans le journal d’audit](media/audit-log-search.png)
- Pour afficher les événements pour les activités exécutées à l’aide d’applets de requête, sélectionnez **afficher les résultats pour toutes les activités** dans la liste **activités** . Si vous connaissez le nom de l’opération pour ces activités, recherchez toutes les activités, puis filtrez les résultats en entrant le nom de l’opération dans la zone de la colonne **activité** . Pour en savoir plus, reportez-vous à [l’étape 3 : filtrer les résultats de la recherche](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results).
- Pour effacer les critères de recherche actuels, cliquez sur **Effacer**. La plage de dates revient à la valeur par défaut des sept derniers jours. Vous pouvez également cliquer sur **tout effacer pour afficher les résultats pour toutes les activités** et annuler toutes les activités sélectionnées.
- Si 5 000 est trouvé, vous pouvez probablement supposer qu’il y a plus de 5 000 événements qui répondent aux critères de recherche. Vous pouvez affiner les critères de recherche et relancer la recherche pour renvoyer moins de résultats, ou vous pouvez exporter tous les résultats de recherche en sélectionnant **Exporter les résultats**pour  >  **Télécharger tous les résultats**.

Regardez [cette vidéo](https://www.youtube.com/embed/UBxaRySAxyE) pour utiliser la recherche dans le journal audio. Rejoignez Ansuman Acharya, responsable de programme pour Teams, comme il montre comment effectuer une recherche dans le journal d’audit pour les équipes.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Utiliser la sécurité des applications Cloud pour définir les stratégies d’activité

Grâce à l’intégration de la sécurité de l' [application Cloud de Microsoft](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) , vous pouvez définir des [stratégies d’activité](https://docs.microsoft.com/cloud-app-security/user-activity-policies) pour appliquer une large gamme de processus automatisés au moyen des API du fournisseur d’applications. Ces stratégies vous permettent de surveiller des activités spécifiques effectuées par divers utilisateurs, ou de suivre des tarifs inattendus d’un certain type d’activité.

Après avoir défini une stratégie de détection d’activité, elle commence à générer des alertes. Les alertes sont générées uniquement sur les activités effectuées après la création de la stratégie. Voici quelques exemples de scénarios d’utilisation des stratégies d’activité dans la sécurité des applications Cloud pour surveiller les activités des équipes.

### <a name="external-user-scenario"></a>Scénario d’utilisateur externe

Dans le cas d’un scénario d’entreprise, l’ajout d’utilisateurs externes à votre environnement d’équipes peut être un scénario. Si les utilisateurs externes sont activés, il est recommandé de surveiller leur présence.  Vous pouvez utiliser la [sécurité des applications Cloud](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) pour identifier les menaces potentielles.

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsExternalUserAddPolicy.png)

La capture d’écran de cette stratégie pour contrôler l’ajout d’utilisateurs externes vous permet d’attribuer un nom à la stratégie, de définir la gravité en fonction des besoins de votre entreprise, de la définir comme (dans ce cas) sur une activité unique, puis de définir les paramètres qui surveilleront uniquement l’ajout d’utilisateurs non internes et limiter cette activité aux équipes.

Les résultats de cette stratégie peuvent être affichés dans le journal d’activité :

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsExternalUserList.png)

Dans cette section, vous pouvez passer en revue les correspondances à la stratégie que vous avez définie et procéder aux modifications nécessaires ou exporter les résultats pour les utiliser ailleurs.

### <a name="mass-delete-scenario"></a>Scénario de suppression massive

Comme mentionné plus haut, vous pouvez surveiller des scénarios de suppression. Il est possible de créer une stratégie qui surveillerait la suppression massive des sites d’équipe. Dans cet exemple, une stratégie basée sur une alerte est configurée pour détecter la suppression massive d’équipes dans une durée de 30 minutes.

![Capture d’écran de la page de création d’une stratégie montrant la création d’une stratégie pour la détection de suppression d’équipe en masse](media/TeamsMassDeletePolicy.png)

Comme le montre la capture d’écran, vous pouvez définir de nombreux paramètres différents pour cette stratégie afin de surveiller les suppressions d’équipe, y compris la gravité, l’action unique ou répétée, et les paramètres limitant ce paramètre à la suppression des équipes et des sites. Cette opération peut être réalisée indépendamment d’un modèle, ou vous avez peut-être créé un modèle sur lequel baser cette stratégie, en fonction des besoins de votre organisation.

Après avoir établi une stratégie qui fonctionnera pour votre entreprise, vous pouvez passer en revue les résultats dans le journal d’activité en tant qu’événements déclenchés :

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsMassDeleteList.png)

Vous pouvez filtrer vers le bas jusqu’à la stratégie que vous avez définie pour afficher les résultats de cette stratégie. Si les résultats que vous obtenez dans le journal d’activité ne sont pas satisfaisants (il est possible que vous voyiez un grand nombre de résultats ou qu’il n’y en ait pas du tout), cela peut vous aider à peaufiner la requête afin de la rendre plus pertinente pour ce que vous en avez besoin.

### <a name="alert-and-governance-scenario"></a>Scénario d’alerte et de gouvernance

Vous pouvez définir des alertes et envoyer des courriers électroniques aux administrateurs et aux autres utilisateurs lorsqu’une stratégie d’activité est déclenchée. Vous pouvez définir des actions de gouvernance automatisées, telles que la suspension d’un utilisateur ou la connexion d’un utilisateur de manière automatique. Cet exemple montre comment un compte d’utilisateur peut être suspendu lorsqu’une stratégie d’activité est déclenchée et détermine qu’un utilisateur a supprimé au moins deux équipes dans 30 minutes.

![Capture d’écran de l’action alertes et gouvernance pour une stratégie d’activité](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Utiliser la sécurité des applications Cloud pour définir les stratégies de détection d’anomalies

Dans le cadre de la sécurité de l’application Cloud, les [stratégies de détection des anomalies](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy) fournissent aux utilisateurs et aux utilisateurs intégrés une analyse comportementale (UEBA) et des formations informatiques (ml), afin que vous puissiez immédiatement exécuter une détection avancée des menaces dans votre environnement Cloud. Étant donné qu’ils sont automatiquement activés, les nouvelles stratégies de détection d’anomalies fournissent des résultats immédiats en fournissant des détections immédiates, ciblant de nombreuses anomalies comportementales au sein de vos utilisateurs, et les ordinateurs et appareils connectés à votre réseau. De plus, les nouvelles stratégies exposent davantage de données à partir du moteur de détection de la sécurité des applications Cloud pour vous aider à accélérer le processus d’examen et contenir les menaces actuelles.

Nous travaillons à l’intégration des événements d’équipes dans des stratégies de détection d’anomalie. Pour le moment, vous pouvez configurer des stratégies de détection d’anomalie pour d’autres produits Office et effectuer des actions sur des utilisateurs qui répondent à ces stratégies.

## <a name="teams-activities"></a>Activités dans teams

Voici la liste de tous les événements enregistrés pour les activités des utilisateurs et des administrateurs dans teams dans le journal d’audit Microsoft 365. Le tableau comprend le nom convivial affiché dans la colonne **activités** et le nom de l’opération correspondante qui s’affiche dans les informations détaillées d’un enregistrement d’audit et dans le fichier CSV lorsque vous exportez les résultats de recherche.

|Nom convivial  |Opération|Description |
|---------|---------|---------|
|Robot ajouté à une équipe   |BotAddedToTeam        |Un utilisateur ajoute un robot à une équipe.        |
|Ajout d'un canal   |ChannelAdded         |Un utilisateur ajoute un canal à une équipe.         |
|Connecteur ajouté  |ConnectorAdded          |Un utilisateur ajoute un connecteur à un canal.        |
|Membres ajoutés    |MemberAdded         |Un propriétaire d’équipe ajoute des membres à une équipe, un canal ou une discussion de groupe.         |
|Onglet ajouté    |TabAdded         |Un utilisateur ajoute un onglet à un canal.        |
|Paramètre de canal modifié    |ChannelSettingChanged         |L’opération ChannelSettingChanged est journalisée lorsque les activités suivantes sont effectuées par un membre de l’équipe. Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses) s’affiche dans la colonne **Item** des résultats de la recherche dans le journal d’audit. <ul><li>Change le nom d’un canal d’équipe (Channel**Name**).</li><li>Modifie la description d’un canal d’équipe (Channel**Description**).</li> </ul>      |
|Paramètre d’organisation modifié   |TeamsTenantSettingChanged         |L’opération TeamsTenantSettingChanged est journalisée lorsque les activités suivantes sont effectuées par un administrateur global dans le centre d’administration 365 Microsoft. Ces activités affectent les paramètres des équipes à l’échelle de l’organisation. Pour en savoir plus, voir [gérer les paramètres d’équipe pour votre organisation](enable-features-office-365.md). <br>Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses) s’affiche dans la colonne **Item** des résultats de la recherche dans le journal d’audit.<ul><li>Active ou désactive les équipes pour l’organisation (**Microsoft teams**).</li><li>Active ou désactive l’interopérabilité entre Microsoft teams et Skype entreprise pour l’organisation (**interopérabilité entre Skype entreprise**).</li><li>Active ou désactive l’affichage de l’organigramme dans les clients Microsoft Teams (**org Chart View**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe de planifier des réunions privées (**Private Meeting Scheduling**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe de planifier des réunions de canal (**Channel Meeting Scheduling**).</li><li>Active ou désactive les appels vidéo pendant les réunions d’équipes (**Video for Skype meetings**).</li><li>Active ou désactive le partage d’écran dans Microsoft teams pendant microsoftteams pour l’organisation (le**partage d’écran pour les réunions Skype**).</li><li>Active ou désactive la possibilité d’ajouter des images animées (appelées Giphys) aux conversations d’équipe (**images animées**).</li><li>Modifie le paramètre d’évaluation du contenu pour l’organisation (**Content Rating**). L’évaluation du contenu restreint les types d’images animées qui peuvent être affichés dans les conversations.</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des images personnalisables (appelées mèmess personnalisés) à partir d’Internet aux conversations d’équipe (**images personnalisables à partir d’Internet**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des images modifiables (appelées autocollants) aux conversations d’équipe (**images modifiables**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’utiliser des robots dans les conversations et les canaux de Microsoft Teams (**org-Wide bots)**.</li><li>Active les robots spécifiques de Microsoft Teams. Ce n’est pas le cas pour le T-bot, qui est le robot qui est disponible lorsque les robots sont activés pour l’organisation (**robots individuels**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des extensions ou des onglets (**extensions ou onglets**).</li><li>Active ou désactive le chargement latéral des robots propriétaires de Microsoft Teams (**chargement latéral des robots**).</li><li>Active ou désactive la possibilité pour les utilisateurs d’envoyer des messages électroniques à un canal Microsoft Teams (**canal de courrier**).</li></ul>|
|Rôle modifié de membres de l’équipe    |MemberRoleChanged         |Le propriétaire d’une équipe change le rôle des membres d’une équipe. Les valeurs suivantes indiquent le type de rôle affecté à l’utilisateur. <br><br>**1** -indique le rôle propriétaire.<br>**2** -indique le rôle membre.<br>**3** -indique le rôle invité.<br><br>La propriété Members comprend également le nom de votre organisation et l’adresse e-mail du membre.        |
|Paramètre d’équipe modifié    |TeamSettingChanged        |L’opération TeamSettingChanged est journalisée lorsque les activités suivantes sont effectuées par un propriétaire d’équipe. Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses) s’affiche dans la colonne **Item** des résultats de la recherche dans le journal d’audit.<ul><li>Change le type d’accès d’une équipe. Les équipes peuvent être définies comme privées ou publiques (**type d’accès d’équipe**). Lorsqu’une équipe est privée (paramètre par défaut), les utilisateurs peuvent accéder à l’équipe uniquement par invitation. Lorsqu’une équipe est publique, elle est détectable par quiconque.</li><li>Modifie la classification des informations d’une équipe (**Team classification**). Par exemple, les données d’une équipe peuvent être classées comme ayant un impact élevé sur l’entreprise, ou avoir un impact faible sur l’activité.</li><li>Modifie le nom d’une équipe (**Team Name**).</li><li>Modifie la description de l’équipe (**Team Description**).</li><li>Modifications apportées aux paramètres de l’équipe. Pour accéder à ces paramètres, le propriétaire d’une équipe peut cliquer avec le bouton droit sur une équipe, sélectionner **gérer l’équipe**, puis cliquez sur l’onglet **paramètres** . Pour ces activités, le nom du paramètre modifié s’affiche dans la colonne **Item** des résultats de la recherche dans le journal d’audit.</li></ul>         |
|Équipe créée    |TeamCreated         |Un utilisateur crée une équipe.         |
|Suppression de toutes les applications de l’Organisation|DeletedAllOrganizationApps           |Suppression de toutes les applications de l’organisation du catalogue.     |
|Application supprimée |AppDeletedFromCatalog           |Une application a été supprimée du catalogue.     |
|Canal supprimé     |ChannelDeleted         |Un utilisateur supprime un canal d’une équipe.         |
|Équipe supprimée  |TeamDeleted            |Un propriétaire d’équipe supprime une équipe.      |
|Application installée |AppInstalled         |L’application a été installée.   |
|Action réalisée sur la carte|PerformedCardAction|Un utilisateur a effectué une action sur une carte adaptative dans une conversation. Les cartes adaptatives sont généralement utilisées par les robots pour permettre l’affichage complet des informations et de l’interaction des conversations. <br/><br/>**Remarque :** Seules les actions d’entrée insérées sur une carte adaptative dans une discussion seront disponibles dans le journal d’audit. Par exemple, lorsqu’un utilisateur envoie une réponse à une interrogation dans une conversation de canal sur une carte adaptative générée par un robot d’interrogation. Les actions de l’utilisateur telles que « afficher le résultat », qui ouvre une boîte de dialogue ou les actions de l’utilisateur dans les boîtes de dialogue ne seront pas disponibles dans le journal d’audit.|
|Application publiée |AppPublishedToCatalog           |Une application a été ajoutée au catalogue.     |
|Robot supprimé de l’équipe   |BotRemovedFromTeam         |Un utilisateur supprime un robot d’une équipe.       |
|Connecteur supprimé     |ConnectorRemoved         |Un utilisateur supprime un connecteur d’un canal.         |
|Membres supprimés    |MemberRemoved        |Le propriétaire d’une équipe supprime les membres d’une équipe, d’un canal ou d’une conversation de groupe.         |
|Onglet supprimé    |TabRemoved         |Un utilisateur supprime un onglet d’un canal.         |
|Application désinstallée |AppUninstalled           |Une application a été désinstallée.     |
|Application mise à jour |AppUpdatedInCatalog           |Une application a été mise à jour dans le catalogue.     |
|Connecteur mis à jour    |ConnectorUpdated         |Un utilisateur a modifié un connecteur dans un canal.         |
|Onglet mise à jour   |TabUpdated         |Un utilisateur a modifié un onglet dans un canal.         |
|Application mise à niveau |AppUpgraded           |Une application a été mise à niveau vers la dernière version dans le catalogue.     |
|Utilisateur connecté à teams     |TeamsSessionStarted         |Un utilisateur se connecte à un client Microsoft Teams. Cet événement ne capture pas les activités d’actualisation des jetons.         |

## <a name="shifts-in-teams-activities"></a>Équipes dans les activités d’équipe

**(version d’évaluation)**

Si votre organisation utilise l’application Shifts dans Microsoft Teams, vous pouvez effectuer une recherche dans le journal d’audit pour les activités liées à l’application Shifts. Vous trouverez ci-dessous une liste de tous les événements qui sont enregistrés pour les activités de décalage dans teams dans le journal d’audit Microsoft 365.

|Nom convivial  |Opération  |Description  |
|---------|---------|---------|
|Groupe planification ajouté      |SchedulingGroupAdded          |Un utilisateur a correctement ajouté un nouveau groupe de planification au planning.          |
|Groupe planification modifié     |SchedulingGroupEdited         |Un utilisateur a modifié un groupe de planification.          |
|Groupe de planification supprimé         |SchedulingGroupDeleted              |Un utilisateur a correctement supprimé un groupe de planification de l’échéancier.|
|Shift ajouté      |ShiftAdded          |Un utilisateur a correctement ajouté une équipe.           |
|Shift modifié       |ShiftEdited       |Un utilisateur a correctement modifié une équipe.        |
|Décalage supprimé          |ShiftDeleted          | Un utilisateur a correctement supprimé une équipe.               |
|Congés ajoutés      |TimeOffAdded          |Un utilisateur a correctement ajouté du temps sur le planning.          |
|Congés modifiés         |TimeOffEdited           |Un utilisateur a correctement modifié des congés.          |
|Congés supprimés     |TimeOffDeleted              |Un utilisateur a correctement supprimé des congés.           |
|Ouverture du quart d’ouverture     |OpenShiftAdded          |Un utilisateur a ajouté une équipe ouverte à un groupe de planification.          |
|Ouverture du quart d’ouverture    |OpenShiftEdited          |Un utilisateur a modifié une équipe ouverte dans un groupe de planification.          |
|Ouverture du quart d’ouverture      |OpenShiftDeleted          |Un utilisateur a correctement supprimé une équipe ouverte d’un groupe de planification.         |
|Planification partagée     |ScheduleShared                  |Un utilisateur a correctement partagé une planification d’équipe pour une plage de dates.          |
|Horloge avec horloge         |ClockedIn          |Un utilisateur pointe correctement à l’aide de Time Time.          |
|À partir de l’horloge      |ClockedOut          |Un utilisateur a correctement pointé à l’aide de Time Time.          |
|Arrêt du démarrage à l’aide de Time Clock      |Événement breakstarted          |Un utilisateur réussit un arrêt au cours d’une session d’horloge active.          |
|Arrêt de fin avec horloge    |BreakEnded          |Un utilisateur termine correctement un arrêt au cours d’une session d’horloge active.          |
|Entrée horaire ajoutée     |TimeClockEntryAdded          |Un utilisateur a correctement ajouté une nouvelle entrée d’horloge dans la feuille de temps.          |
|Entrée horaire modifiée     | TimeClockEntryEdited             |Un utilisateur a modifié une entrée Time Clock dans la feuille de temps.          |
|Entrée de l’heure de suppression    |TimeClockEntryDeleted              |Un utilisateur a correctement supprimé une entrée Time Clock dans une feuille de temps.          |
|Demande de Shift ajoutée         |RequestAdded              |Un utilisateur a ajouté une demande de Shift.          |
|Réponse à une demande de Shift     |RequestRespondedTo                  |Un utilisateur a répondu à une demande de Shift.          |
|Demande de Shift annulée         |RequestCanceled               |Un utilisateur a annulé une demande de Shift.          |
|Paramètre de planification modifié      |ScheduleSettingChanged          |Un utilisateur modifie un paramètre dans les paramètres de décalage.         |
|Intégration de main-d’œuvre ajoutée      |WorkforceIntegrationAdded                  | Le changement d’application est intégré à un système tiers.         |
|A accepté le message Shift         |OffShiftDialogAccepted          |Un utilisateur confirme le message hors décalage pour accéder aux équipes après les heures de travail.           |

## <a name="office-365-management-activity-api"></a>API activité de gestion d’Office 365

Vous pouvez utiliser l’API activité de gestion d’Office 365 pour récupérer des informations sur les événements d’équipe. Pour en savoir plus sur le schéma de l’API activité de gestion pour Teams, voir [schéma d’équipe](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).


## <a name="attribution-in-teams-audit-logs"></a>Attribution dans les journaux d’audit d’équipes

Pour l’instant, il existe un problème connu relatif à l’attribution dans les journaux d’audit d’équipes et aux messages de contrôle : un propriétaire peut être mal attribué à la suppression ou à l’ajout d’utilisateurs. Cela se produit lorsque le changement intervient en dehors de teams. Dans ces cas, nous vous recommandons d’utiliser les [journaux d’audit d’Office 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="related-topics"></a>Voir aussi

- [Effectuer une recherche dans le journal d’audit dans le centre de conformité Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 
