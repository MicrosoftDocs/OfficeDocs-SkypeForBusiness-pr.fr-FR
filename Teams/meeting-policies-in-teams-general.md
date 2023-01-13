---
title: Gérer les stratégies de réunion générale
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres de stratégie de réunion générale dans Teams.
ms.openlocfilehash: a2fea38c20ab20a735810d228cfeee571d3fdfca
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69799940"
---
# <a name="meeting-policy-settings---general"></a>Paramètres de stratégie de réunion : général

<a name="bkgeneral"> </a>

Cet article décrit les paramètres de stratégie généraux suivants pour les réunions Teams :

- [Se réunir maintenant dans les canaux](#meet-now-in-channels)
- [Complément Outlook](#outlook-add-in)
- [Planification des réunions de canal](#channel-meeting-scheduling)
- [Planification de réunions privées](#private-meeting-scheduling)
- [Rapport d’engagement](#engagement-report)
- [Inscription à une réunion](#meeting-registration)
- [Séminaires web](#webinars)
- [Fournisseur de réunion pour le mode Îles](#meeting-provider-for-islands-mode)
- [Réactions aux réunions](#meeting-reactions)
- [Coach de l’orateur](#speaker-coach)

## <a name="meet-now-in-channels"></a>Se réunir maintenant dans les canaux

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si un utilisateur peut démarrer une réunion non planifiée dans un canal Teams. Si vous activez ce paramètre, les utilisateurs peuvent cliquer sur le bouton **Réunion** pour démarrer une réunion non planifiée ou planifier une réunion dans le canal. Ce paramètre est activé par défaut.

[![Capture d’écran montrant l’icône Conférence maintenant sous un message.](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Complément Outlook

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les réunions Teams peuvent être planifiées à partir d’Outlook (Windows, Mac, web et mobile).

![Capture d’écran montrant la possibilité de planifier une nouvelle réunion.](media/meeting-policies-outlook-add-in.png)

Si vous désactivez ce paramètre, les utilisateurs ne peuvent pas planifier de réunions Teams lorsqu’ils créent une réunion dans Outlook. Par exemple, dans Outlook sur Windows, l’option **Nouvelle réunion Teams** ne s’affiche pas dans le ruban.

## <a name="channel-meeting-scheduling"></a>Planification des réunions de canal

Utilisez la stratégie AllowChannelMeetingScheduling existante pour contrôler les types d’événements qu’il est possible de créer dans les calendriers d’équipe. Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier une réunion dans un canal Teams. Par défaut, ce paramètre est activé.

Si cette stratégie est désactivée, les utilisateurs ne peuvent pas créer de réunions de canal. Toutefois, les réunions existantes des canaux existants peuvent être modifiées par l’organisateur de l’événement.

L’option Planifier une réunion sera désactivée.

![Capture d’écran montrant l’option Planifier une réunion dans Teams.](media/schedule-meeting-option.png)

La sélection de canal est désactivée.

[![Capture d’écran montrant l’option calendrier permettant de sélectionner un canal dans lequel vous souhaitez planifier une réunion.](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Dans la page des publications de canal, les fonctionnalités suivantes sont désactivées :

- Bouton **Planifier une réunion** dans la zone composer une réponse du canal.
  ![Capture d’écran montrant l’option calendrier permettant de sélectionner un canal dans lequel vous souhaitez planifier une réunion.](media/schedule-meeting-disabled-in-chat2.png)
  
- Bouton **planifier une réunion** sur l’en-tête de canal.
  ![Capture d’écran montrant l’option de calendrier permettant de sélectionner un canal via lequel vous souhaitez planifier une réunion.](media/schedule-now-in-header.png)

Dans le calendrier de canal :

- Le bouton **Ajouter un événement** dans l’en-tête du calendrier est désactivé.
  ![Capture d’écran montrant l’option de calendrier permettant de sélectionner un canal qui vous permettra de planifier une réunion.](media/add-new-event-disabled.png)

- Les utilisateurs ne peuvent pas faire glisser et sélectionner un bloc horaire sur le calendrier du canal pour créer une réunion de canal.

- Les utilisateurs ne peuvent pas utiliser les raccourcis clavier pour créer une réunion dans le calendrier par canal.

Dans le centre d’administration :

L’application Calendrier du canal s’affiche dans la section **Applications Microsoft** sur la page stratégies d’autorisation d’application.

![Capture d’écran montrant la stratégie d’autorisations d’application dans le Centre d’administration Teams.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Planification de réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier des réunions privées en Teams. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe. **La planification des réunions privées** est activée par défaut.

Si vous désactivez les paramètres **Planification des réunions privées** et Planification des **réunions de canal** , les options **Ajouter des participants requis** et **Ajouter un canal** sont désactivées pour les utilisateurs dans Teams.

## <a name="engagement-report"></a>Rapport d’engagement

Il s’agit d’une stratégie par utilisateur. Ce paramètre contrôle si les organisateurs de réunion peuvent télécharger le [rapport d’engagement de réunion](teams-analytics-and-reports/meeting-attendance-report.md).

Cette stratégie est activée par défaut et permet à vos organisateurs de voir qui s’est inscrit et a participé aux réunions et webinaires qu’ils ont configurés. Pour la désactiver dans le Centre d’administration Teams, accédez à **Stratégies de réunion des réunions** >  et définissez le paramètre **rapport d’engagement** sur **Désactivé**.

Vous pouvez également modifier une stratégie de réunion Teams existante à l’aide de l’applet de [commande Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Par défaut, le paramètre **AllowEngagementReport** est défini sur **Activé** dans PowerShell. Pour empêcher un organisateur de réunion de télécharger le rapport d’engagement de réunion, définissez le paramètre **AllowEngagementReport** sur **Désactivé**.

Lorsque cette stratégie est activée, l’option de téléchargement du rapport d’engagement de réunion s’affiche dans le volet **Participants** .

> [!NOTE]
> En tant qu’administrateur, vous ne pouvez pas afficher le rapport de présence pour les réunions que vous n’organisez pas. Toutefois, vous pouvez afficher les détails des participants pour une réunion donnée dans les 24 heures suivant cette réunion. Dans le Centre d’administration Teams, accédez à **Utilisateurs** > **Gérer les utilisateurs**. Choisissez le nom d’affichage de l’organisateur de la réunion. Sélectionnez l’onglet **Réunions & appels** , puis choisissez l’ID de réunion ou l’ID d’appel approprié. Ensuite, sélectionnez **Détails du participant**.

Pour plus d’informations, notamment sur les limites du rapport d’engagement, consultez [affichage et téléchargement des rapports de participation aux réunions dans Teams](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310).

## <a name="meeting-registration"></a>Inscription à une réunion

Il s’agit d’une stratégie par utilisateur. Si vous activez ce paramètre, les utilisateurs de votre organisation peuvent ajouter l’inscription à une réunion. Cette stratégie est activée par défaut.

Pour en savoir plus sur l’inscription aux réunions, consultez [Configurer l’inscription aux réunions](set-up-webinars.md#configure-meeting-registration).

## <a name="webinars"></a>Séminaires web

Il s’agit d’une stratégie par utilisateur. Si vous activez les webinaires, les utilisateurs de votre organisation peuvent créer des webinaires avec une gestion robuste des inscriptions, des sites d’inscription et d’événements personnalisables et des options de réunion par défaut orientées événements. Cette stratégie est activée par défaut.

Pour plus d’informations sur les webinaires, consultez [Configurer des webinaires](set-up-webinars.md).

Pour plus d’informations sur les différences entre les réunions, les webinaires et les événements en direct, consultez [Réunions, webinaires et événements en direct](quick-start-meetings-live-events.md).

## <a name="meeting-provider-for-islands-mode"></a>Fournisseur de réunion pour le mode Îles

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine quel complément de réunion Outlook est utilisé pour *les utilisateurs en mode îles*. Vous pouvez spécifier si les utilisateurs peuvent utiliser uniquement le complément réunion Teams ou les deux compléments réunion et Skype® Entreprise pour planifier des réunions dans Outlook.

Vous ne pouvez appliquer cette stratégie uniquement aux utilisateurs qui sont en mode Îles et dont le paramètre **AllowOutlookAddIn** est défini sur **True** dans leur stratégie de réunion Teams.

Pour l’instant, vous pouvez uniquement utiliser PowerShell pour définir cette stratégie. Vous pouvez modifier une stratégie de réunion Teams existante à l’aide de l’applet de commande [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour spécifier le complément de la réunion que vous voulez mettre à la disposition des utilisateurs, définissez le paramètre **PreferredMeetingProviderForIslandsMode** comme suit :

- Définir le paramètre sur **TeamsAndSfB** pour activer le complément réunion Teams et Skype® Entreprise dans Outlook. **TeamsAndSfB** est la valeur par défaut.
- Définir le paramètre sur **Teams** pour activer uniquement le complément réunion équipes dans Outlook. Ce paramètre de stratégie permet de s’assurer que toutes les réunions ultérieures ont un lien participer à une réunion Teams. Il ne migre pas les liens de jointure de réunion Skype Entreprise existants vers Teams. Ce paramètre de stratégie n’affecte pas les fonctionnalités de présence, de conversation, d’appel RTC ou d’autres fonctionnalités de Skype Entreprise, ce qui signifie que les utilisateurs continueront à utiliser Skype Entreprise pour ces fonctionnalités.

  Si vous avez défini le paramètre sur **Teams**, puis revenez à **TeamsAndSfB**, les deux compléments de réunion sont activés. Cependant, notez que les liens de réunion Teams existants ne seront pas migrés vers Skype Entreprise. Seules les réunions Skype Entreprise planifiées après la modification auront un lien de jointure de réunion Skype Entreprise.

## <a name="meeting-reactions"></a>Réactions aux réunions

La disponibilité des réactions aux réunions peut être configurée via l’interface du centre d’administration Teams ou à l’aide de PowerShell. Les réactions aux réunions sont activées par défaut.

Dans le Centre d’administration Teams, les réactions aux réunions peuvent être activées ou désactivées sous les **stratégies de**  >  réunion sous la section **Participants & invités** d’une stratégie de réunion.

Pour configurer le paramètre dans PowerShell, utilisez l’applet de [commande Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Pour la désactiver, définissez **AllowMeetingReactions** sur **False**.

La désactivation des réactions pour un utilisateur ne signifie pas qu’un utilisateur ne peut pas utiliser de réactions dans les réunions qu’il planifie. L’organisateur de la réunion peut toujours activer les réactions à partir de la page des options de réunion, quel que soit le paramètre par défaut.

## <a name="speaker-coach"></a>Coach de l’orateur

Ce paramètre permet aux utilisateurs d’activer le Coach du présentateur pendant une réunion Teams. Speaker Coach écoute l’audio de l’utilisateur pendant sa présentation et fournit des commentaires privés en temps réel et des suggestions d’amélioration. L’utilisateur reçoit également un rapport de synthèse de ses commentaires après la réunion.

> [!NOTE]
> L’utilisateur qui a activé l’assistant coach pendant la réunion est le seul à pouvoir voir le rapport de synthèse des commentaires. Les administrateurs n’ont accès à aucune de ces données.

Actuellement, vous pouvez uniquement définir et modifier cette stratégie dans PowerShell. à l’aide de l’applet de [commande Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Ce paramètre est activé par défaut. Pour la désactiver, définissez **AllowMeetingCoach** sur **False**.

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Affecter des stratégies dans Teams](policy-assignment-overview.md)
- [Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs](meeting-policies-restricted-anonymous-access.md)
