---
title: Rechercher des événements Microsoft Teams dans le journal d'audit
description: Découvrez comment récupérer des données Microsoft Teams à partir du journal d’audit dans le portail de conformité Microsoft Purview.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- audit
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7219ee11f6818890b8be34f42f76dfa26ef0d12
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950441"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Rechercher des événements Microsoft Teams dans le journal d'audit

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Le journal d’audit peut vous aider à examiner des activités spécifiques dans les services Microsoft 365. Pour Microsoft Teams, voici quelques-unes des activités auditées :

- Création d'une équipe
- Suppression d'une équipe
- Ajout d'un canal
- Canal supprimé
- Paramètre de canal modifié

Pour obtenir la liste complète des activités Teams auditées, consultez [Activités Teams](#teams-activities) et [Plannings dans les activités Teams](#shifts-in-teams-activities).

> [!NOTE]
> Les événements d’audit des canaux privés sont également enregistrés tels qu’ils sont pour les équipes et les canaux standard.

## <a name="turn-on-auditing-in-teams"></a>Activer l’audit dans Teams

Avant de pouvoir examiner les données d’audit, vous devez d’abord activer l’audit dans le portail de conformité Microsoft Purview. Pour plus d’informations, consultez [Activer ou désactiver l’audit](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> Les données d’audit ne sont disponibles qu’à partir du point où vous avez activé l’audit.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Récupérer des données Teams à partir du journal d'audit

1. Pour récupérer les journaux d’audit des activités Teams, accédez à <https://compliance.microsoft.com> et sélectionnez **Auditer**.

2. Dans la page **Rechercher** , filtrez les activités, les dates et les utilisateurs que vous souhaitez auditer.

3. Pour une analyse plus approfondie, exportez les résultats dans Excel.

Pour obtenir des instructions pas à pas, consultez [Rechercher dans le journal d’audit dans le centre de conformité](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

> [!IMPORTANT]
> Les données d’audit ne sont visibles dans le journal d’audit que si l’audit est activé.

La durée pendant laquelle un enregistrement d’audit est conservé et peut faire l’objet d’une recherche dans le journal d’audit dépend de votre abonnement Microsoft 365 ou Office 365, et en particulier du type de licence attribué aux utilisateurs. Pour plus d’informations, consultez la [description du service Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Conseils pour la recherche dans le journal d’audit

Voici des conseils pour rechercher des activités Teams dans le journal d’audit.

:::image type="content" alt-text="Capture d’écran de la page de recherche dans le journal d’audit dans le centre de conformité" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- Vous pouvez sélectionner des activités spécifiques à rechercher en cliquant sur la case à cocher en regard d’une ou plusieurs activités. Si une activité est sélectionnée, vous pouvez cliquer dessus pour annuler la sélection. Vous pouvez également utiliser la zone de recherche pour afficher les activités qui contiennent le mot clé que vous tapez.

  ![Capture d’écran de la liste déroulante des activités sur la page de recherche du journal d’audit](media/audit-log-search.png)

- Pour afficher les événements des activités exécutées à l’aide d’applets de commande, sélectionnez **Afficher les résultats de toutes les activités** dans la liste **Activités** . Si vous connaissez le nom de l’opération pour ces activités, tapez-le dans la zone de recherche pour afficher l’activité, puis sélectionnez-la.

- Pour effacer les critères de recherche actuels, cliquez sur **Effacer tout**. La plage de dates revient à la valeur par défaut des sept derniers jours.

- Si 5 000 résultats sont trouvés, vous pouvez probablement supposer que plus de 5 000 événements répondent aux critères de recherche. Vous pouvez affiner les critères de recherche et réexécuter la recherche pour renvoyer moins de résultats, ou vous pouvez exporter tous les résultats de la recherche en sélectionnant **Exporter** > **Télécharger tous les résultats**. Pour obtenir des instructions pas à pas sur l’exportation des journaux d’audit, consultez [Exporter les résultats de la recherche dans un fichier](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file).

Regardez [cette vidéo](https://www.youtube.com/embed/UBxaRySAxyE) sur l’utilisation de la recherche dans les journaux audio. Rejoignez Ansuman Acharya, responsable de programme pour Teams, car il montre comment effectuer une recherche dans les journaux d’audit pour Teams.

## <a name="teams-activities"></a>Activités Teams

Voici une liste de tous les événements enregistrés pour les activités des utilisateurs et des administrateurs dans Teams dans le journal d’audit Microsoft 365. Le tableau inclut le nom convivial affiché dans la colonne **Activités** et le nom de l’opération correspondante qui apparaît dans les informations détaillées d’un enregistrement d’audit et dans le fichier CSV lorsque vous exportez les résultats de la recherche.

|**Nom convivial**|**Opération**|**Description**|
|:----------------|:------------|:--------------|
|Ajout du bot à l’équipe|BotAddedToTeam|Un utilisateur ajoute un bot à une équipe.|
|Ajout d'un canal|ChannelAdded|Un utilisateur ajoute un canal à une équipe.|
|Connecteur ajouté|ConnecteurAdded|Un utilisateur ajoute un connecteur à un canal.|
|Ajout de détails sur la réunion Teams <sup>2</sup>|MeetingDetail|Teams a ajouté des informations sur une réunion, notamment l’heure de début, l’heure de fin et l’URL pour rejoindre la réunion.|
|Ajout d’informations sur les participants à la réunion <sup>2</sup>|MeetingParticipantDetail|Teams a ajouté des informations sur les participants d’une réunion, y compris l’ID utilisateur de chaque participant, l’heure à laquelle un participant a rejoint la réunion et l’heure à laquelle un participant a quitté la réunion.|
|Membres ajoutés|MemberAdded|Un propriétaire d’équipe ajoute des membres à une équipe, un canal ou une conversation de groupe.|
|Onglet ajouté|TabAdded|Un utilisateur ajoute un onglet à un canal.|
| Étiquette de confidentialité appliquée | SensitivityLabelApplied | Un utilisateur ou un organisateur de réunion a appliqué une étiquette de confidentialité à une réunion Teams. |
|Paramètre de canal modifié|ChannelSettingChanged|L’opération ChannelSettingChanged est journalisée lorsque les activités suivantes sont effectuées par un membre de l’équipe. Pour chacune de ces activités, une description du paramètre qui a été modifié (indiquée entre parenthèses est affichée dans la colonne **Élément** dans les résultats de la recherche dans le journal d’audit. <ul><li>Modifie le nom d’un canal d’équipe (**nom du canal**)</li><li>Modification de la description d’un canal d’équipe (**description du canal**)</li> </ul>|
|Paramètre d’organisation modifié|TeamsTenantSettingChanged|L’opération TeamsTenantSettingChanged est journalisée lorsque les activités suivantes sont effectuées par un administrateur général dans le Centre d'administration Microsoft 365. Ces activités affectent les paramètres Teams à l’échelle de l’organisation. Pour en savoir plus, consultez [Gérer les paramètres Teams pour votre organisation](enable-features-office-365.md). <br>Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses) s’affiche dans la colonne **Élément** des résultats de la recherche dans le journal d’audit.<ul><li>Active ou désactive Teams pour l’organisation (**Microsoft Teams**).</li><li>Active ou désactive l’interopérabilité entre Microsoft Teams et Skype Entreprise pour l’organisation (**interopérabilité Skype Entreprise**).</li><li>Active ou désactive l’affichage organigramme dans les clients Microsoft Teams (**vue Organigramme**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe de planifier des réunions privées (**planification de réunions privées**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe de planifier des réunions de canal (**planification des réunions de canal**).</li><li>Active ou désactive les appels vidéo dans les réunions Teams (**vidéo pour les réunions Skype**).</li><li>Active ou désactive le partage d’écran dans les réunions Microsoft Teams pour l’organisation (**partage d’écran pour les réunions Skype**).</li><li>Active ou désactive cette possibilité d’ajouter des images animées (appelées Giphys) aux conversations Teams (**images animées**).</li><li>Modifie le paramètre d’évaluation du contenu pour l’organisation (**évaluation du contenu**). L’évaluation du contenu limite le type d’image animée qui peut être affiché dans les conversations.</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des images personnalisables (appelées mèmes personnalisés) à partir d’Internet aux conversations d’équipe (**images personnalisables à partir d’Internet**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des images modifiables (appelées autocollants) aux conversations d’équipe (**images modifiables**).</li><li>Active ou désactive cette possibilité pour les membres de l’équipe d’utiliser des bots dans les conversations et les canaux Microsoft Teams (**bots à l’échelle de l’organisation).**</li><li>Active des bots spécifiques pour Microsoft Teams. Cela n’inclut pas le bot T-Bot, qui est le bot d’aide Teams disponible lorsque les bots sont activés pour l’organisation (**bots individuels**).</li><li>Active ou désactive la possibilité pour les membres de l’équipe d’ajouter des extensions ou des onglets (**extensions ou onglets**).</li><li>Active ou désactive le chargement indépendant de bots propriétaires pour Microsoft Teams (**chargement indépendant de bots**).</li><li>Active ou désactive la possibilité pour les utilisateurs d’envoyer des messages électroniques à un canal Microsoft Teams (**messagerie de canal**).</li></ul>|
|Modification du rôle des membres dans l’équipe|MemberRoleChanged|Un propriétaire d’équipe modifie le rôle des membres d’une équipe. Les valeurs suivantes indiquent le type de rôle attribué à l’utilisateur. <br><br>**1** - Indique le rôle Membre.<br>**2** - Indique le rôle Propriétaire.<br>**3** - Indique le rôle Invité.<br><br>La propriété Members inclut également le nom de votre organisation et l’adresse e-mail du membre.|
|Modification du paramètre d’équipe|TeamSettingChanged|L’opération TeamSettingChanged est journalisée lorsque les activités suivantes sont effectuées par un propriétaire d’équipe. Pour chacune de ces activités, une description du paramètre modifié (entre parenthèses) s’affiche dans la colonne **Élément** des résultats de la recherche dans le journal d’audit.<ul><li>Modifie le type d’accès d’une équipe. Teams peut être défini comme privé ou public (**type d’accès à l’équipe**). Lorsqu’une équipe est privée (paramètre par défaut), les utilisateurs peuvent accéder à l’équipe uniquement sur invitation. Lorsqu’une équipe est publique, elle est détectable par tout le monde.</li><li>Modifie la classification des informations d’une équipe (**classification d’équipe**). Par exemple, les données d’équipe peuvent être classées comme ayant un impact commercial élevé, un impact moyen sur l’activité ou un impact faible sur l’activité.</li><li>Modifie le nom d’une équipe (**nom de l’équipe**).</li><li>Modifie la description de l’équipe (**description de l’équipe**).</li><li>Modifications apportées aux paramètres de l’équipe. Pour accéder à ces paramètres, un propriétaire d’équipe peut cliquer avec le bouton droit sur une équipe, sélectionner **Gérer l’équipe**, puis cliquer sur l’onglet **Paramètres** . Pour ces activités, le nom du paramètre qui a été modifié s’affiche dans la colonne **Élément** des résultats de la recherche dans le journal d’audit.</li></ul>|
| Étiquette de confidentialité modifiée | SensitivityLabelChanged | Un utilisateur a modifié une étiquette de confidentialité sur une réunion Teams. |
|Création d’une conversation <sup>1, </sup> <sup>2</sup>|ChatCreated|Une conversation Teams a été créée.|
|Équipe créée|TeamCreated|Un utilisateur crée une équipe.|
|Suppression d’un message|MessageDeleted|Un message dans une conversation ou un canal a été supprimé.|
|Toutes les applications de l’organisation ont été supprimées|DeletedAllOrganizationApps|Toutes les applications de l’organisation ont été supprimées du catalogue.|
|Application supprimée|AppDeletedFromCatalog|Une application a été supprimée du catalogue.|
|Canal supprimé|ChannelDeleted|Un utilisateur supprime un canal d’une équipe.|
|Équipe supprimée|TeamDeleted|Un propriétaire d’équipe supprime une équipe.|
|Modification d’un message avec un lien URL dans Teams|MessageEditedHasLink|Un utilisateur modifie un message et y ajoute un lien URL dans Teams.|
|Messages exportés <sup>1, </sup> <sup>2</sup>|MessagesExported|Les messages de conversation ou de canal ont été exportés.|
|Échec de la validation de l’invitation au canal partagé<sup>3</sup>|FailedValidation|Un utilisateur répond à une invitation à un canal partagé, mais la validation de l’invitation a échoué.|
|Conversation récupérée <sup>1, </sup> <sup>2</sup>|ChatRetrieved|Une conversation Microsoft Teams a été récupérée.|
|Extrait tout le contenu hébergé d’un message<sup>1, </sup> <sup>2</sup>|MessageHostedContentsListed|Tout le contenu hébergé dans un message, tel que les images ou les extraits de code, a été récupéré.|
|Application installée|AppInstalled|Une application a été installée.|
|Action effectuée sur la carte|PerformCardAction|Un utilisateur a effectué une action sur une carte adaptative dans une conversation. Les cartes adaptatives sont généralement utilisées par les bots pour permettre l’affichage complet des informations et des interactions dans les conversations. <br/><br/>**Note:** Seules les actions d’entrée inline sur une carte adaptative à l’intérieur d’une conversation sont disponibles dans le journal d’audit. Par exemple, lorsqu’un utilisateur envoie une réponse au sondage dans une conversation de canal sur une carte adaptative générée par un bot de sondage. Les actions utilisateur telles que « Afficher le résultat », qui ouvre une boîte de dialogue, ou les actions de l’utilisateur à l’intérieur des dialogues ne sont pas disponibles dans le journal d’audit.|
|Publication d’un nouveau message <sup>1, </sup> <sup>2</sup>|MessageSent|Un nouveau message a été publié sur une conversation ou un canal.|
|Application publiée|AppPublishedToCatalog|Une application a été ajoutée au catalogue.|
|Lire un message <sup>1, </sup> <sup>2</sup>|MessageRead|Un message d’une conversation ou d’un canal a été récupéré.|
|Lire le contenu hébergé d’un message <sup>1, </sup> <sup>2</sup>|MessageHostedContentRead|Le contenu hébergé dans un message, tel qu’une image ou un extrait de code, a été récupéré.|
|Bot supprimé de l’équipe|BotRemovedFromTeam|Un utilisateur supprime un bot d’une équipe.|
|Connecteur supprimé|ConnecteurRemoved|Un utilisateur supprime un connecteur d’un canal.|
|Membres supprimés|MemberRemoved|Un propriétaire d’équipe supprime des membres d’une équipe, d’un canal ou d’une conversation de groupe.|
| Étiquette de confidentialité supprimée | SensitivityLabelRemoved | Un utilisateur a supprimé une étiquette de confidentialité d’une réunion Teams. |
|Suppression du partage du canal<sup>d’équipe 3</sup>|TerminatedSharing|Un propriétaire d’équipe ou de canal a désactivé le partage pour un canal partagé.|
|Partage restauré du canal<sup>d’équipe 3</sup>|SharingRestored|Un propriétaire d’équipe ou de canal a réactivé le partage pour un canal partagé.|
|Onglet Supprimé|TabRemoved|Un utilisateur supprime un onglet d’un canal.|
|Réponse à l’invitation pour le canal partagé<sup>3</sup>|InviteeResponded|Un utilisateur a répondu à une invitation de canal partagé.|
|Réponse à la réponse de l’invité au canal partagé<sup>3</sup>|ChannelOwnerResponded|Un propriétaire de canal a répondu à une réponse d’un utilisateur qui a répondu à une invitation de canal partagé.|
|Messages récupérés <sup>1, </sup> <sup>2</sup>|MessagesListed|Les messages d’une conversation ou d’un canal ont été récupérés.|
|Envoi d’un message avec un lien URL dans Teams|MessageCreatedHasLink|Un utilisateur envoie un message contenant un lien URL dans Teams.|
|Notification de modification envoyée pour la création de message <sup>1, </sup> <sup>2</sup>|MessageCreatedNotification|Une notification de modification a été envoyée pour notifier un nouveau message à une application d’écouteur abonnée.|
|Notification de modification envoyée pour la suppression du message <sup>1, </sup> <sup>2</sup>|MessageDeletedNotification|Une notification de modification a été envoyée pour avertir une application d’écouteur abonnée d’un message supprimé.|
|Notification de modification envoyée pour les mises à jour <sup>de message 1, </sup> <sup>2</sup>|MessageUpdatedNotification|Une notification de modification a été envoyée pour avertir une application d’écouteur abonnée d’un message mis à jour.|
|Invitation envoyée pour le canal partagé<sup>3</sup>|InviteSent|Un propriétaire ou un membre de canal envoie une invitation à un canal partagé. Les invitations aux canaux partagés peuvent être envoyées à des personnes extérieures à votre organisation si la stratégie de canal est configurée pour partager le canal avec des utilisateurs externes.|
|Abonné aux notifications de modification de message <sup>1, </sup> <sup>2</sup>|SubscribedToMessages|Un abonnement a été créé par une application d’écouteur pour recevoir des notifications de modification pour les messages.|
|Application désinstallée|AppUninstalled|Une application a été désinstallée.|
|Application mise à jour|AppUpdatedInCatalog|Une application a été mise à jour dans le catalogue.|
|Mise à jour d’une conversation <sup>1, </sup> <sup>2</sup>|ChatUpdated|Une conversation Teams a été mise à jour.|
|Mise à jour d’un message <sup>1, </sup> <sup>2</sup>|MessageUpdated|Un message d’une conversation ou d’un canal a été mis à jour.|
|Connecteur mis à jour|ConnectorUpdated|Un utilisateur a modifié un connecteur dans un canal.|
|Onglet Mis à jour|TabUpdated|Un utilisateur a modifié un onglet dans un canal.|
|Application mise à niveau|AppUpgraded|Une application a été mise à niveau vers sa dernière version dans le catalogue.|
|Utilisateur connecté à Teams|TeamsSessionStarted|Un utilisateur se connecte à un client Microsoft Teams. Cet événement ne capture pas les activités d’actualisation des jetons.|

> [!NOTE]
> <sup>1</sup> Un enregistrement d’audit pour cet événement n’est enregistré que lorsque l’opération est effectuée en appelant un API Graph Microsoft. Si l’opération est effectuée dans le client Teams, aucun enregistrement d’audit n’est enregistré<br/><sup>2</sup> Cet événement est disponible uniquement dans Audit (Premium). Cela signifie que les utilisateurs doivent se voir attribuer la licence appropriée avant que ces événements soient enregistrés dans le journal d’audit. Pour plus d’informations sur les activités disponibles uniquement dans Audit (Premium), consultez [Audit (Premium) dans Microsoft Purview](/microsoft-365/compliance/advanced-audit#advanced-audit-events). Pour connaître les exigences de licence d’audit (Premium), consultez [Audit des solutions dans Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements). <br/> <sup>3</sup> Cet événement est en préversion publique.

## <a name="shifts-in-teams-activities"></a>Changements dans les activités Teams

**(version d’évaluation)**

Si votre organisation utilise l’application Shifts dans Teams, vous pouvez rechercher dans le journal d’audit des activités liées à l’application Shifts. Voici une liste de tous les événements enregistrés pour les activités Shifts dans Teams dans le journal d’audit Microsoft 365.

|Nom convivial|Opération|Description|
|---|---|---|
|Ajout d’un groupe de planification|ScheduleGroupAdded|Un utilisateur a correctement ajouté un nouveau groupe de planification à la planification.|
|Groupe de planification modifié|ScheduleGroupEdited|Un utilisateur modifie correctement un groupe de planification.|
|Groupe de planification supprimé|ScheduleGroupDeleted|Un utilisateur supprime correctement un groupe de planification de la planification de la planification.|
|Planification retirée|ScheduleWithdrawn|Un utilisateur retire correctement une planification publiée.|
|Ajout d’un décalage|MajAdded|Un utilisateur a correctement ajouté un décalage.|
|Maj modifié|ShiftEdited|Un utilisateur modifie correctement un shift.|
|Décalage supprimé|MajDeleted|Un utilisateur supprime correctement une équipe.|
|Ajout d’un congé|TimeOffAdded|Un utilisateur a correctement ajouté un congé à la planification.|
|Temps de congé modifié|TimeOffEdited|Un utilisateur modifie correctement le temps de congé.|
|Congé supprimé|TimeOffDeleted|Un utilisateur supprime correctement le temps de congé.|
|Ajout du décalage ouvert|OpenShiftAdded|Un utilisateur a correctement ajouté un shift ouvert à un groupe de planification.|
|Maj ouvert modifié|OpenShiftEdited|Un utilisateur modifie correctement une équipe ouverte dans un groupe de planification.|
|Décalage ouvert supprimé|OpenShiftDeleted|Un utilisateur supprime correctement une équipe ouverte d’un groupe de planification.|
|Planification partagée|ScheduleShared|Un utilisateur a partagé avec succès une planification d’équipe pour une plage de dates.|
|Horloge dans à l’aide de Time clock|ClockedIn|Un utilisateur a réussi à horloger à l’aide de Time clock.|
|Horloge à l’aide de Time clock|ClockedOut|Un utilisateur a réussi à sortir de l’horloge à l’aide de Time clock.|
|Arrêt démarré à l’aide de l’horloge chronologique|BreakStarted|Un utilisateur démarre correctement une pause pendant une session d’horloge active.|
|Arrêt terminé à l’aide de l’horloge chronologique|BreakEnded|Un utilisateur met fin à une pause pendant une session d’horloge active.|
|Ajout de l’entrée Time clock|TimeClockEntryAdded|Un utilisateur a correctement ajouté une nouvelle entrée d’horloge manuelle sur la feuille de temps.|
|Entrée d’horloge de temps modifiée|TimeClockEntryEdited|Un utilisateur modifie correctement une entrée d’horloge sur la feuille de temps.|
|Entrée d’horloge de l’heure supprimée|TimeClockEntryDeleted|Un utilisateur supprime correctement une entrée Time clock sur la feuille de temps.|
|Ajout d’une demande de shift|RequestAdded|Un utilisateur a ajouté une demande de shift.|
|Réponse à la demande de shift|RequestRespondedTo|Un utilisateur a répondu à une demande de shift.|
|Demande de shift annulée|RequestCancelled|Un utilisateur a annulé une demande de shift.|
|Modification du paramètre de planification|ScheduleSettingChanged|Un utilisateur modifie un paramètre dans les paramètres Shifts.|
|Intégration de la main-d’œuvre ajoutée|WorkforceIntegrationAdded|L’application Shifts est intégrée à un système tiers.|
|Message de décalage accepté|OffShiftDialogAccepted|Un utilisateur accuse réception du message d’arrêt de travail pour accéder à Teams après les heures de travail.|

## <a name="office-365-management-activity-api"></a>API d’activité de gestion Office 365

Vous pouvez utiliser l’API d’activité de gestion Office 365 pour récupérer des informations sur les événements Teams. Pour en savoir plus sur le schéma de l’API d’activité de gestion pour Teams, consultez [Schéma Teams](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Attribution dans les journaux d’audit Teams

Les modifications d’appartenance à Teams (telles que les utilisateurs ajoutés ou supprimés) effectuées via Azure Active Directory (Azure AD), le portail d’administration Microsoft 365 ou Groupes Microsoft 365 API Graph s’affichent dans les messages d’audit Teams et dans le canal Général avec une attribution à un propriétaire existant de l’équipe, et non à l’initiateur réel de l’action. Dans ces scénarios, consultez les journaux d’audit d’Azure AD ou [de Groupe Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) pour voir les informations pertinentes.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Utiliser Defender for Cloud Apps pour définir des stratégies d’activité

À [l’aide de Microsoft Defender for Cloud Apps’intégration](/cloud-app-security/what-is-cloud-app-security), vous pouvez définir des [stratégies d’activité](/cloud-app-security/user-activity-policies) pour appliquer un large éventail de processus automatisés à l’aide des API du fournisseur d’applications. Ces stratégies vous permettent de surveiller des activités spécifiques effectuées par différents utilisateurs, ou de suivre des taux inattendus élevés d’un certain type d’activité.

Une fois que vous avez défini une stratégie de détection d’activité, elle commence à générer des alertes. Les alertes sont générées uniquement sur les activités qui se produisent après la création de la stratégie. Voici quelques exemples de scénarios permettant d’utiliser des stratégies d’activité dans Defender for Cloud Apps pour surveiller les activités Teams.

### <a name="external-user-scenario"></a>Scénario d’utilisateur externe

L’un des scénarios sur lesquels vous souhaiterez peut-être garder un œil, du point de vue métier, est l’ajout d’utilisateurs externes à votre environnement Teams. Si les utilisateurs externes sont activés, la surveillance de leur présence est une bonne idée.  Vous pouvez utiliser [Defender for Cloud Apps pour](/cloud-app-security/what-is-cloud-app-security) identifier les menaces potentielles.

:::image type="content" alt-text="Stratégie de surveillance de l’ajout d’utilisateurs externes." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

La capture d’écran de cette stratégie pour surveiller l’ajout d’utilisateurs externes vous permet de nommer la stratégie, de définir la gravité en fonction des besoins de votre entreprise, de la définir comme (dans ce cas) une seule activité, puis d’établir les paramètres qui surveilleront spécifiquement uniquement l’ajout d’utilisateurs non internes et limiter cette activité à Teams.

Les résultats de cette stratégie peuvent être affichés dans le journal d’activité :

:::image type="content" alt-text="Événements déclenchés par la stratégie des utilisateurs externes." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

Ici, vous pouvez passer en revue les correspondances à la stratégie que vous avez définie et effectuer les ajustements nécessaires, ou exporter les résultats pour les utiliser ailleurs.

### <a name="mass-delete-scenario"></a>Scénario de suppression en masse

Comme mentionné précédemment, vous pouvez surveiller les scénarios de suppression. Il est possible de créer une stratégie qui surveillerait la suppression massive des sites Teams. Dans cet exemple, une stratégie basée sur les alertes est configurée pour détecter la suppression massive d’équipes en 30 minutes.

:::image type="content" alt-text="Stratégie montrant la configuration d’une stratégie pour la détection de suppression d’équipe de masse." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

Comme le montre la capture d’écran, vous pouvez définir de nombreux paramètres différents pour cette stratégie afin de surveiller les suppressions de Teams, notamment la gravité, l’action unique ou répétée et les paramètres limitant ce paramètre à La suppression de sites et teams. Cette opération peut être effectuée indépendamment d’un modèle, ou vous pouvez avoir créé un modèle sur lequel baser cette stratégie, en fonction des besoins de votre organisation.

Après avoir établi une stratégie qui fonctionne pour votre entreprise, vous pouvez examiner les résultats dans le journal d’activité à mesure que des événements sont déclenchés :

:::image type="content" alt-text="Capture d’écran des événements déclenchés par des suppressions en masse." source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

Vous pouvez filtrer jusqu’à la stratégie que vous avez définie pour afficher les résultats de cette stratégie. Si les résultats que vous obtenez dans le journal d’activité ne sont pas satisfaisants (peut-être que vous voyez beaucoup de résultats, ou rien du tout), cela peut vous aider à affiner la requête pour la rendre plus pertinente par rapport à ce que vous avez besoin de faire.

### <a name="alert-and-governance-scenario"></a>Scénario d’alerte et de gouvernance

Vous pouvez définir des alertes et envoyer des e-mails aux administrateurs et autres utilisateurs lorsqu’une stratégie d’activité est déclenchée. Vous pouvez définir des actions de gouvernance automatisées, telles que la suspension d’un utilisateur ou le fait qu’un utilisateur se reconnecte de manière automatisée. Cet exemple montre comment suspendre un compte d’utilisateur lorsqu’une stratégie d’activité est déclenchée et détermine qu’un utilisateur a supprimé au moins deux équipes en 30 minutes.

![Capture d’écran des alertes et des actions de gouvernance pour une stratégie d’activité.](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Utiliser Defender for Cloud Apps pour définir des stratégies de détection d’anomalie

Les [stratégies de détection des anomalies](/cloud-app-security/anomaly-detection-policy) dans Defender for Cloud Apps fournissent des analyses comportementales d’utilisateur et d’entité prêtes à l’emploi (UEBA) et du Machine Learning (ML) afin que vous puissiez exécuter immédiatement la détection avancée des menaces dans votre environnement cloud. Comme elles sont automatiquement activées, les nouvelles stratégies de détection d’anomalies fournissent des résultats immédiats en fournissant des détections immédiates, ciblant de nombreuses anomalies comportementales sur vos utilisateurs et les machines et appareils connectés à votre réseau. En outre, les nouvelles stratégies exposent davantage de données à partir du moteur de détection Defender for Cloud Apps, pour vous aider à accélérer le processus d’investigation et à contenir les menaces en cours.

Nous travaillons à l’intégration des événements Teams dans les stratégies de détection d’anomalies. Pour l’instant, vous pouvez configurer des stratégies de détection d’anomalie pour d’autres produits Office et prendre des mesures sur les utilisateurs qui correspondent à ces stratégies.

## <a name="related-topics"></a>Rubriques connexes

- [Rechercher dans le journal d’audit dans le portail de conformité Microsoft Purview](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
