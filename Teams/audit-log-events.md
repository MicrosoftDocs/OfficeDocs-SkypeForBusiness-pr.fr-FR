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
description: Découvrez comment récupérer des données Microsoft Teams à partir du journal d’audit dans le Centre de conformité Microsoft 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26427bb7026c586c9493e023f127a43923325cfa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092622"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Rechercher des événements Microsoft Teams dans le journal d'audit

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Le journal d’audit peut vous aider à examiner des activités spécifiques au sein des services Microsoft 365. Pour Microsoft Teams, voici quelques-unes des activités auditées :

- Création d'une équipe
- Suppression d'une équipe
- Ajout d'un canal
- Modification d'un paramètre

Pour obtenir la liste complète des activités [](#teams-activities) teams auditées, consultez les activités et shifts dans les activités [Teams (en prévisualisation).](#shifts-in-teams-activities)

> [!NOTE]
> Les événements d’audit des canaux privés sont également enregistrés tels qu’ils sont pour les équipes et les canaux standard.

## <a name="turn-on-auditing-in-teams"></a>Activer l’audit dans Teams

Avant d’examiner les données d’audit, vous devez d’abord activer l’audit dans le Centre [& conformité.](https://protection.office.com) Pour obtenir de l’aide sur l’activer, voir Activer ou désactiver la recherche dans le journal [d’audit.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

> [!IMPORTANT]
> Les données d’audit sont uniquement disponibles à partir du moment où vous avez désactivé l’audit.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Récupérer des données Teams à partir du journal d'audit

1. Pour récupérer les journaux d’audit, accédez au [Centre de sécurité et de conformité](https://go.microsoft.com/fwlink/?linkid=855775). Sous **Recherche,** sélectionnez **Recherche dans le journal d’audit.**

2. Utilisez l’option **Rechercher** pour filtrer les données en fonction des activités, dates et utilisateurs que vous souhaitez vérifier.

3. Pour une analyse plus approfondie, exportez les résultats dans Excel.

> [!IMPORTANT]
> Les données d’audit ne sont visibles que dans le journal d’audit si l’audit est désactivé.

La durée pendant la rétention et la recherche d’un enregistrement d’audit dans le journal d’audit dépend de votre abonnement Microsoft 365 ou Office 365 et plus spécifiquement du type de licence affecté aux utilisateurs. Pour en savoir plus, consultez la [description du service du Centre & conformité.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="tips-for-searching-the-audit-log"></a>Conseils pour rechercher dans le journal d’audit

Voici quelques conseils pour rechercher des activités de Teams dans le journal d’audit.

![Capture d’écran de la page de recherche dans le journal d’audit](media/audit-log-search-page.png)

- Vous pouvez sélectionner des activités spécifiques à rechercher en cliquant sur le nom de l’activité. Vous pouvez également rechercher toutes les activités d’un groupe (par exemple, activités sur les fichiers et les **dossiers)** en cliquant sur le nom du groupe. Si une activité est sélectionnée, vous pouvez cliquer dessus pour annuler la sélection. Vous pouvez également utiliser la zone de recherche pour afficher les activités qui contiennent le mot clé que vous tapez.

  ![Capture d’écran de la recherche dans le journal d’audit](media/audit-log-search.png)

- Pour afficher des événements pour des activités qui s’exécutent à l’aide d’lets de cmdlets, sélectionnez Afficher les résultats **pour toutes** les activités dans la **liste Activités.** Si vous connaissez le nom de l’opération pour ces activités, recherchez toutes les activités, puis filtrez les résultats en tapant le nom de l’opération dans la zone de la colonne **Activité.** Pour en savoir plus, voir [l’étape 3 : filtrer les résultats de recherche.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results)

- Pour effacer les critères de recherche actuels, cliquez sur **Effacer.** La plage de dates reprend la valeur par défaut des sept derniers jours. Vous pouvez également cliquer **sur Effacer tout pour afficher les résultats de toutes les activités** afin d’annuler toutes les activités sélectionnées.

- Si 5 000 résultats sont trouvés, vous pouvez partir du principe que plus de 5 000 événements ont répondu aux critères de recherche. Vous pouvez affiner les critères de recherche et réexécuter la recherche pour renvoyer moins de résultats, ou exporter tous les résultats de recherche en sélectionnant **Exporter** les résultats  >  **Télécharger tous les résultats.**

Regardez cette [vidéo pour utiliser](https://www.youtube.com/embed/UBxaRySAxyE) la recherche dans le journal audio. Rejoignez Ansuman Acharya, un responsable de programme pour Teams, qui montre comment effectuer une recherche dans le journal d’audit pour Teams.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Utiliser la sécurité des applications cloud pour définir des stratégies d’activité

À l’aide de l’intégration de [Microsoft Cloud App Security,](/cloud-app-security/what-is-cloud-app-security) vous pouvez définir des stratégies d’activité pour appliquer un large éventail de processus automatisés à l’aide des API du fournisseur d’application. [](/cloud-app-security/user-activity-policies) Ces stratégies vous permettent de surveiller des activités spécifiques effectuées par différents utilisateurs ou de suivre des taux élevés inattendus pour un certain type d’activité.

Une fois que vous avez définie une stratégie de détection d’activité, elle commence à générer des alertes. Les alertes sont uniquement générées sur les activités qui se produisent une fois que vous avez créé la stratégie. Voici quelques exemples d’utilisation des stratégies d’activité dans la sécurité de l’application Cloud pour surveiller les activités de Teams.

### <a name="external-user-scenario"></a>Scénario d’utilisateur externe

Un scénario que vous voudrez peut-être garder à l’œil, du point de vue de l’entreprise, est l’ajout d’utilisateurs externes à votre environnement Teams. Si les utilisateurs externes sont activés, il est bon de surveiller leur présence.  Vous pouvez utiliser la [sécurité de l’application cloud](/cloud-app-security/what-is-cloud-app-security) pour identifier les menaces potentielles.

![Capture d’écran d’une liste d’événements déclenchés par des suppressions de masse](media/TeamsExternalUserAddPolicy.png)

La capture d’écran de cette stratégie pour surveiller l’ajout d’utilisateurs externes vous permet de nommer la stratégie, de définir la gravité en fonction des besoins de votre entreprise, de la définir en tant qu’activité unique (dans ce cas), puis d’établir les paramètres qui surveilleront spécifiquement l’ajout d’utilisateurs non internes et limiteront cette activité à Teams.

Les résultats de cette stratégie peuvent être vus dans le journal d’activité :

![Capture d’écran d’une liste d’événements déclenchés par des suppressions de masse](media/TeamsExternalUserList.png)

Vous pouvez passer en revue les correspondances à la stratégie que vous avez définie et apporter les ajustements nécessaires, ou exporter les résultats pour les utiliser ailleurs.

### <a name="mass-delete-scenario"></a>Scénario de suppression de masse

Comme mentionné précédemment, vous pouvez surveiller les scénarios de suppression. Il est possible de créer une stratégie qui surveille la suppression de masse des sites Teams. Dans cet exemple, une stratégie basée sur les alertes est définie pour détecter la suppression de masse des équipes sur une période de 30 minutes.

![Capture d’écran de la page Créer une stratégie montrant la configuration d’une stratégie pour la détection de la suppression de masse des équipes](media/TeamsMassDeletePolicy.png)

Comme le montre la capture d’écran, vous pouvez définir de nombreux paramètres différents pour cette stratégie afin de surveiller la gravité des suppressions d’équipes, notamment la gravité, les actions simples ou répétées et les paramètres qui limitent cette action à Teams et à la suppression de site. Cette fonction peut être effectuée indépendamment d’un modèle, ou vous pouvez créer un modèle pour baser cette stratégie sur les besoins de votre organisation.

Après avoir établi une stratégie qui fonctionne pour votre entreprise, vous pouvez examiner les résultats dans le journal d’activité à mesure que les événements sont déclenchés :

![Capture d’écran d’une liste d’événements déclenchés par des suppressions de masse](media/TeamsMassDeleteList.png)

Vous pouvez filtrer vers le bas jusqu’à la stratégie que vous avez définie pour voir ses résultats. Si les résultats que vous avez obtenus dans le journal d’activité ne sont pas satisfaisants (vous voyez peut-être un grand nombre de résultats ou rien du tout), cela peut vous aider à affiner la requête pour la rendre plus pertinente par rapport à ce que vous devez faire.

### <a name="alert-and-governance-scenario"></a>Scénario d’alerte et de gouvernance

Vous pouvez définir des alertes et envoyer des courriers électroniques aux administrateurs et aux autres utilisateurs lorsqu’une stratégie d’activité est déclenchée. Vous pouvez définir des actions de gouvernance automatisées, telles que la suspension d’un utilisateur ou le fait de faire en sorte qu’un utilisateur se connecte à nouveau de manière automatisée. Cet exemple montre comment un compte d’utilisateur peut être suspendu lorsqu’une stratégie d’activité est déclenchée et détermine qu’un utilisateur a supprimé plusieurs équipes en 30 minutes.

![Capture d’écran des alertes et des actions de gouvernance pour une stratégie d’activité](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Utiliser la sécurité de l’application cloud pour définir les stratégies de détection des détections

[](/cloud-app-security/anomaly-detection-policy) Les stratégies de détection anormale dans la sécurité des applications cloud offrent des données d’analyse de l’environnement de l’utilisateur et de l’entité (UEBA) et de l’apprentissage automatique (ML) prédictives, de sorte que vous pouvez exécuter immédiatement la détection avancée des menaces dans votre environnement cloud. Étant donné qu’elles sont activées automatiquement, les nouvelles stratégies de détection anormale fournissent des résultats immédiats en fournissant des détections immédiates, en ciblant de nombreuses relationurs au sein de vos utilisateurs, ainsi que les ordinateurs et appareils connectés à votre réseau. De plus, les nouvelles stratégies exposent davantage de données provenant du moteur de détection de la sécurité des applications cloud, afin de vous aider à accélérer le processus d’examen et à contenir des menaces en cours.

Nous travaillons à l’intégration des événements Teams dans les stratégies de détection anormale. Pour l’instant, vous pouvez définir des stratégies de détection anormales pour d’autres produits Office et prendre des mesures sur les utilisateurs qui correspondent à ces stratégies.

## <a name="teams-activities"></a>Activités dans Teams

Voici une liste de tous les événements enregistrés pour les activités utilisateur et administrateur dans Teams dans le journal d’audit Microsoft 365. Le tableau inclut le nom convivial  affiché dans la colonne Activités et le nom de l’opération correspondante qui apparaît dans les informations détaillées d’un enregistrement d’audit et dans le fichier CSV lorsque vous exportez les résultats de la recherche.

|Nom convivial  |Opération|Description |
|---------|---------|---------|
|Robot ajouté à l’équipe   |BotAddedToTeam        |Un utilisateur ajoute un robot à une équipe.        |
|Ajout d'un canal   |ChannelAdded         |Un utilisateur ajoute un canal à une équipe.         |
|Connecteur ajouté  |ConnectorAdded          |Un utilisateur ajoute un connecteur à un canal.        |
|Membres ajoutés    |MemberAdded         |Un propriétaire d’équipe ajoute des membres à une équipe, un canal ou une conversation de groupe.         |
|Onglet ajouté    |TabAdded         |Un utilisateur ajoute un onglet à un canal.        |
|Paramètre de canal modifié    |ChannelSettingChanged         |L’opération ChannelSettingChanged est consignée lorsque les activités suivantes sont effectuées par un membre de l’équipe. Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses s’affiche dans la colonne Élément des résultats de la recherche dans le journal d’audit).  <ul><li>Change name of a team channel (**Channel name)**</li><li>Description des modifications d’un canal d’équipe **(description du canal)**</li> </ul>      |
|Paramètre d’organisation modifié   |TeamsTenantSettingChanged         |L’opération TeamsTenantSettingChanged est consignée lorsque les activités suivantes sont effectuées par un administrateur global dans le Centre d’administration Microsoft 365. Ces activités affectent les paramètres Teams à l’échelle de l’organisation. Pour en savoir plus, [consultez Gérer les paramètres Teams de votre organisation.](enable-features-office-365.md) <br>Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses) s’affiche dans la colonne Élément des résultats de la recherche dans le journal d’audit. <ul><li>Active ou désactive Teams pour l’organisation **(Microsoft Teams).**</li><li>Active ou désactive l’interopérabilité entre Microsoft Teams et Skype Entreprise pour l’organisation **(interopérabilité** de Skype Entreprise).</li><li>Active ou désactive l’affichage d’organigramme dans les clients Microsoft Teams **(Affichage d’organigramme).**</li><li>Active ou désactive la possibilité pour les membres de l’équipe de planifier des réunions privées **(planification de réunion privée).**</li><li>Active ou désactive la possibilité pour les membres de l’équipe de planifier des réunions de canal **(planification de réunions de canal).**</li><li>Active ou désactive les appels vidéo dans les réunions Teams **(Vidéo pour les réunions Skype).**</li><li>Active ou désactive le partage d’écran dans les réunions Microsoft Teams pour l’organisation (partage d’écran **pour les réunions Skype).**</li><li>Active ou désactive la possibilité d’ajouter des images animées (appelées Giphys) aux conversations Teams (**Images animées).**</li><li>Modifie le paramètre d’évaluation du contenu pour l’organisation **(Évaluation du contenu).** L’évaluation du contenu restreint le type d’image animée qui peut être affiché dans les conversations.</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des images personnalisables (appelées mèmes personnalisés) à partir d’Internet aux conversations d’équipe (images personnalisables à partir **d’Internet).**</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des images modifiables (appelées autocollants) aux conversations d’équipe **(images modifiables).**</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’utiliser des bots dans les conversations et canaux Microsoft Teams **(bots à l’échelle de l’organisation).**</li><li>Active des robots spécifiques pour Microsoft Teams. Cela n’inclut pas T-Bot, qui est le robot d’aide de Teams disponible lorsque les bots sont activés pour l’organisation **(bots individuels).**</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des extensions ou des onglets **(extensions ou onglets).**</li><li>Active ou désactive le chargement latéral des robots propriétaires pour Microsoft Teams **(chargement latéral des bots).**</li><li>Active ou désactive la possibilité pour les utilisateurs d’envoyer des messages électroniques à un canal Microsoft Teams **(messagerie de canal).**</li></ul>|
|Rôle modifié des membres de l’équipe    |MemberRoleChanged         |Un propriétaire d’équipe modifie le rôle des membres d’une équipe. Les valeurs suivantes indiquent le type de rôle attribué à l’utilisateur. <br><br>**1** - Indique le rôle Membre.<br>**2** - Indique le rôle Propriétaire.<br>**3** - Indique le rôle Invité.<br><br>La propriété Membres inclut également le nom de votre organisation et l’adresse de courrier du membre.        |
|Paramètre d’équipe modifié    |TeamSettingChanged        |L’opération TeamSettingChanged est consignée lorsque les activités suivantes sont effectuées par un propriétaire d’équipe. Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses) s’affiche dans la colonne Élément des résultats de la recherche dans le journal d’audit. <ul><li>Modifie le type d’accès pour une équipe. Les équipes peuvent être définies comme privées ou publiques **(type d’accès à l’équipe).** Quand une équipe est privée (paramètre par défaut), les utilisateurs ne peuvent y accéder que sur invitation. Quand une équipe est publique, n’importe qui peut la découvrir.</li><li>Modifie la classification des informations d’une équipe **(Classification d’équipe).** Par exemple, les données d’équipe peuvent être classées comme impact élevé, impact moyen ou faible sur l’entreprise.</li><li>Modifie le nom d’une équipe **(Nom de l’équipe).**</li><li>Modifie la description de l’équipe **(Description de l’équipe).**</li><li>Modifications apportées aux paramètres de l’équipe. Pour accéder à ces paramètres, un propriétaire d’équipe peut cliquer avec le bouton droit sur une équipe, sélectionner Gérer l’équipe, puis cliquer sur **l’onglet Paramètres.** Pour ces activités, le nom du paramètre modifié s’affiche dans la colonne **Élément** des résultats de la recherche dans le journal d’audit.</li></ul>         |
|Équipe créée    |TeamCreated         |Un utilisateur crée une équipe.         |
|Toutes les applications de l’organisation ont été supprimées|DeletedAllOrganizationApps           |Toutes les applications de l’organisation ont été supprimées du catalogue.     |
|Application supprimée |AppDeletedFromCatalog           |Une application a été supprimée du catalogue.     |
|Canal supprimé     |ChannelDeleted         |Un utilisateur supprime un canal d’une équipe.         |
|Équipe supprimée  |TeamDeleted            |Un propriétaire d’équipe supprime une équipe.      |
|Application installée |AppInstalled         |Une application a été installée.   |
|Action effectuée sur la carte|PerformedCardAction|Un utilisateur a fait une action sur une carte adaptative dans une conversation. Les cartes adaptatives sont généralement utilisées par les bots pour permettre l’affichage enrichi des informations et de l’interaction dans les conversations. <br/><br/>**Remarque :** Seules les actions d’entrée en ligne sur une carte adaptative à l’intérieur d’une conversation seront disponibles dans le journal d’audit. Par exemple, lorsqu’un utilisateur envoie une réponse de sondage dans une conversation de canal sur une carte adaptative générée par un bot de sondage. Les actions de l’utilisateur telles que « Afficher le résultat », qui ouvre une boîte de dialogue, ou les actions de l’utilisateur à l’intérieur de boîtes de dialogue ne seront pas disponibles dans le journal d’audit.|
|Application publiée |AppPublishedToCatalog           |Une application a été ajoutée au catalogue.     |
|Robot supprimé de l’équipe   |BotRemovedFromTeam         |Un utilisateur supprime un robot d’une équipe.       |
|Connecteur supprimé     |ConnectorRemoved         |Un utilisateur supprime un connecteur d’un canal.         |
|Membres supprimés    |MemberRemoved        |Un propriétaire d’équipe supprime des membres d’une équipe, d’un canal ou d’une conversation de groupe.         |
|Onglet supprimé    |TabRemoved         |Un utilisateur supprime un onglet d’un canal.         |
|Application désinstallée |AppUninstalled           |Une application a été désinstallée.     |
|Application mise à jour |AppUpdatedInCatalog           |Une application a été mise à jour dans le catalogue.     |
|Connecteur mis à jour    |ConnectorUpdated         |Un utilisateur a modifié un connecteur dans un canal.         |
|Onglet Mis à jour   |TabUpdated         |Un utilisateur a modifié un onglet dans un canal.         |
|Application mise à niveau |AppUpgraded           |Une application a été mise à niveau vers sa dernière version dans le catalogue.     |
|Utilisateur inscrit à Teams     |TeamsSessionStarted         |Un utilisateur se signe à un client Microsoft Teams. Cet événement ne capture pas les activités d’actualisation des jetons.         |

## <a name="shifts-in-teams-activities"></a>Shifts dans les activités teams

**(version d’évaluation)**

Si votre organisation utilise l’application Shifts dans Teams, vous pouvez rechercher des activités liées à l’application Shifts dans le journal d’audit. Voici une liste de tous les événements enregistrés pour les activités Shifts dans Teams dans le journal d’audit Microsoft 365.

|Nom convivial  |Opération  |Description  |
|---------|---------|---------|
|Added scheduling group |ScheduleGroupAdded          |Un utilisateur ajoute un nouveau groupe de planification à l’échéancier.|
|Groupe planification modifié     |ScheduleGroupEdited         |Un utilisateur modifie avec succès un groupe de planification.          |
|Groupe de planification supprimé         |ScheduleGroupDeleted              |Un utilisateur supprime un groupe de planification du planning.|
|Échéancier retiré |ScheduleWithwithwith              |Un utilisateur retire un planning publié.|
|Shift ajouté      |ShiftAdded          |Un utilisateur ajoute un shift.           |
|Shift modifié       |ShiftEdited       |Un utilisateur modifie correctement un shift.        |
|Shift supprimé          |ShiftDeleted          | Un utilisateur supprime un shift.               |
|Ajout d’un congé      |TimeOffAdded          |Un utilisateur ajoute un congé au planning.          |
|Congés modifiés         |TimeOffEdited           |Un utilisateur modifie correctement un congé.          |
|Congé supprimé     |TimeOffDeleted              |Un utilisateur supprime un congé.           |
|Shift ouvert ajouté     |OpenShiftAdded          |Un utilisateur ajoute avec succès un shift ouvert à un groupe de planification.          |
|Shift ouvert modifié    |OpenShiftEdited          |Un utilisateur modifie avec succès un shift ouvert dans un groupe de planification.          |
|Shift ouvert supprimé      |OpenShiftDeleted          |Un utilisateur supprime avec succès un shift ouvert dans un groupe de planification.         |
|Planification partagée     |ScheduleShared                  |Un utilisateur a partagé un planning d’équipe pour une plage de dates.          |
|Horloge à l’aide de la horloge         |ClockedIn          |Un utilisateur utilise correctement l’horloge à l’aide de la horloge.          |
|Horloge à l’aide de la horloge      |ClockedOut          |Un utilisateur a réussi à faire son horloge à l’aide de la horloge.          |
|Début d’une pause à l’aide de la Horloge      |BreakStarted          |Un utilisateur démarre avec succès une pause pendant une session d’horloge active.          |
|Pause terminée à l’aide de la Horloge    |BreakEnded          |Un utilisateur met fin à une pause pendant une session d’horloge active.          |
|Entrée Horloge ajoutée     |TimeClockEntryAdded          |Un utilisateur ajoute une nouvelle entrée d’horloge manuelle sur La feuille de temps.          |
|Entrée d’horloge modifiée     | TimeClockEntryEdited             |Un utilisateur modifie avec succès une entrée Point d’horloge sur La Feuille d’heures.          |
|Entrée Deleted Time Clock    |TimeClockEntryDeleted              |Un utilisateur supprime correctement une entrée Time Clock sur Time Sheet.          |
|Demande de shift ajoutée         |RequestAdded              |Un utilisateur a ajouté une demande de shift.          |
|Réponse à une demande de shift     |RequestRespondedTo                  |Un utilisateur a répondu à une demande de shift.          |
|Demande de shift annulée         |RequestCancelled               |Un utilisateur a annulé une demande de shift.          |
|Paramètre de planification modifié      |ScheduleSettingChanged          |Un utilisateur modifie un paramètre dans les paramètres Shifts.         |
|Intégration du personnel ajoutée      |WorkforceIntegrationAdded                  | L’application Shifts est intégrée à un système tiers.         |
|Message De shift accepté         |OffShiftDialogAccepted          |Un utilisateur reconnaît le message d’congé pour accéder à Teams après les heures de travail.           |

## <a name="office-365-management-activity-api"></a>API d’activité de gestion d’Office 365

Vous pouvez utiliser l’API d’activité de gestion d’Office 365 pour récupérer des informations sur les événements Teams. Pour en savoir plus sur le schéma de l’API d’activité de gestion pour Teams, consultez [le schéma Teams.](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema)

## <a name="attribution-in-teams-audit-logs"></a>Attribution dans les journaux d’audit teams

Les changements d’appartenance à Teams (par exemple, les utilisateurs ajoutés ou supprimés) via Azure Active Directory (Azure AD), le portail d’administration Microsoft 365 ou l’API Graph des groupes Microsoft 365 apparaîtront dans les messages d’audit Teams et dans le canal Général avec une attribution à un propriétaire existant de l’équipe, et non au véritable initiateur de l’action. Dans ces scénarios, consultez les journaux d’audit d’Azure AD ou de [groupe Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) pour consulter les informations pertinentes.

## <a name="related-topics"></a>Rubriques connexes

- [Effectuer des recherches dans le journal d’audit dans le Centre de conformité Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)