---
title: Gérer les stratégies générales de réunion
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres généraux de stratégie de réunion dans Teams.
ms.openlocfilehash: b7c08799ee9e7c2b1e6239b17abaa66b7d1e3d47
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61177935"
---
# <a name="meeting-policy-settings---general"></a>Paramètres de stratégie de réunion : général

<a name="bkgeneral"> </a>

Cet article décrit les paramètres de stratégie générale suivants pour Teams réunions :

- [Se réunir maintenant dans des canaux](#meet-now-in-channels)
- [Outlook-in](#outlook-add-in)
- [Planification des réunions de canal](#channel-meeting-scheduling)
- [Planification de réunions privées](#private-meeting-scheduling)
- [Se réunir maintenant dans des réunions privées](#meet-now-in-private-meetings)
- [Mode de rôle de présentateur désigné](#designated-presenter-role-mode)
- [Rapport d’engagement](#engagement-report)
- [Inscription à une réunion](#meeting-registration)
- [Qui pouvez vous inscrire](#who-can-register)
- [Fournisseur de réunion pour le mode Islands](#meeting-provider-for-islands-mode)

## <a name="meet-now-in-channels"></a>Se réunir maintenant dans des canaux

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre contrôle si un utilisateur peut démarrer une réunion ad hoc dans Teams canal. Si vous l’activer, les  utilisateurs peuvent cliquer sur le bouton Réunion pour démarrer une réunion ad hoc ou planifier une réunion dans le canal. La valeur par défaut est True.

[![Capture d’écran montrant l’icône Rencontrer maintenant sous un message. ](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)

## <a name="outlook-add-in"></a>Outlook-in

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les réunions Teams peuvent être planifiées à partir d’Outlook (Windows, Mac, web et mobile).

![Capture d’écran montrant la possibilité de planifier une nouvelle réunion.](media/meeting-policies-outlook-add-in.png)

Si vous la désactiver, les utilisateurs ne peuvent pas planifier Teams réunion lorsqu’ils créent une réunion dans Outlook. Par exemple, dans Outlook sur Windows, l’option **Nouvelle réunion Teams** ne s’affiche pas dans le ruban.

## <a name="channel-meeting-scheduling"></a>Planification des réunions de canal

Utilisez la stratégie AllowChannelMeetingScheduling existante pour contrôler les types d’événements qu’il est possible de créer dans les calendriers d’équipe. Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier une réunion dans un canal Teams. Par défaut, ce paramètre est activé. 

Si cette stratégie est désactivée, les utilisateurs ne pourront pas créer de réunions de canal. Toutefois, les réunions existantes des canaux existants peuvent être modifiées par l’organisateur de l’événement.

L’option Planifier une réunion sera désactivée.

![Capture d’écran montrant l’option Planifier une réunion Teams.](media/schedule-meeting-option.png)

La sélection de canal est désactivée.

[![Capture d’écran montrant l’option de calendrier pour sélectionner un canal dans qui vous voulez planifier une réunion. ](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

Dans la page de billets du canal, les messages suivants sont désactivés :

- Bouton **Planifier une réunion** dans la zone composer une réponse du canal.
  ![Capture d’écran montrant l’option de calendrier pour sélectionner un canal dans lequel vous voulez planifier une réunion.](media/schedule-meeting-disabled-in-chat2.png)
  
- Bouton **planifier une réunion** sur l’en-tête de canal.
  ![Capture d’écran montrant l’option de calendrier pour sélectionner un canal par lequel vous voulez planifier une réunion.](media/schedule-now-in-header.png)

Dans le calendrier de canal :

- Le bouton **Ajouter un événement** dans l’en-tête du calendrier est désactivé.
  ![Capture d’écran montrant l’option de calendrier permettant de sélectionner un canal qui vous permet de planifier une réunion.](media/add-new-event-disabled.png)

- Les utilisateurs ne peuvent pas faire glisser et sélectionner un bloc de temps dans le calendrier du canal pour créer une réunion de canal.

- Les utilisateurs ne peuvent pas utiliser les raccourcis clavier pour créer une réunion dans le calendrier du canal.

Dans le centre d’administration :

L’application Calendrier du canal s’affiche dans la section **Applications Microsoft** sur la page stratégies d’autorisation d’application.

![Capture d’écran montrant la stratégie d’autorisations d’application dans Teams centre d’administration.](media/manage-microsoft-apps-policy.png)

## <a name="private-meeting-scheduling"></a>Planification de réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre détermine si les utilisateurs peuvent planifier des réunions privées en Teams. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.

Notez que si vous désactivez **Autoriser la planification des réunions privées** et **Autoriser la planification des réunions de canal**, les options **Ajouter des participants obligatoires** et **Ajouter un canal** sont désactivées pour les utilisateurs dans Teams. Par défaut, ce paramètre est activé.

## <a name="meet-now-in-private-meetings"></a>Se réunir maintenant dans des réunions privées

Il s’agit d’une stratégie par utilisateur qui s’applique avant le début d’une réunion. Ce paramètre contrôle si un utilisateur peut commencer une réunion privée ad hoc.  Par défaut, ce paramètre est activé.

## <a name="designated-presenter-role-mode"></a>Mode de rôle de présentateur désigné

Il s’agit d’une stratégie par utilisateur. Ce paramètre vous permet de modifier la valeur par défaut du paramètre **Qui peut présenter ?** dans **Options de réunion** dans le client Teams. Ce paramètre de stratégie affecte toutes les réunions, y compris les réunions Conférence maintenant.

Le paramètre **Qui peut présenter ?** permet aux organisateurs de réunions de choisir qui peuvent être présentateurs pendant une réunion. Pour plus d’informations, consulte [Modifier les paramètres des participants pour une réunion Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) et [Rôles dans une réunion Teams](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

Pour l’instant, vous pouvez uniquement utiliser PowerShell pour configurer ce paramètre de stratégie. Vous pouvez modifier une stratégie de réunion Teams existante à l’aide de l’applet de commande [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour spécifier la valeur par défaut du paramètres **Qui peut présenter ?** dans Teams, définissez le paramètre **DesignatedPresenterRoleMode** sur l’un des éléments suivants :

- **EveryoneUserOverride**: tous les participants à la réunion peuvent être présentateurs. Ceci est la valeur par défaut. Ce paramètre correspond au paramètre **Tout le monde** dans Teams.
- **EveryoneInCompanyUserOverride** : les utilisateurs authentifiés au sein de l’organisation, y compris les utilisateurs invités, peuvent être présentateurs. Ce paramètre correspond au paramètre **Contacts dans mon organisation** dans Teams.
- **OrganizerOnlyUserOverride** : seul l’organisateur de la réunion peut être présentateur et tous les participants à la réunion sont désignés comme participants. Ce paramètre correspond au paramètre **Uniquement moi** dans Teams.

Gardez à l’esprit qu’une fois que vous avez défini la valeur par défaut, les organisateurs de réunion peuvent toujours modifier ce paramètre dans Teams et choisir les personnes pouvant présenter les réunions qu’ils planifient.

## <a name="engagement-report"></a>Rapport d’engagement

Il s’agit d’une stratégie par utilisateur. Ce paramètre permet de contrôler si les organisateurs de réunion peuvent télécharger le [Rapport de participation aux réunions](teams-analytics-and-reports/meeting-attendance-report.md).

Cette stratégie est off par défaut et permet à vos organisateurs de voir qui s’est inscrit et a participé aux réunions et webinaires qu’ils ont créés. Pour activer cette fonction dans le centre d Teams réunion, allez dans **Stratégies** de réunion, puis définissez la stratégie  >  sur **Activé.**

Vous pouvez modifier une stratégie de réunion Teams existante à l’aide de l’applet de commande [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour permettre à l’organisateur de la réunion de télécharger le rapport de présence de réunion, définissez le paramètre **AllowEngagementReport** **sur Activé.** Lorsque cette option est activée, l’option permettant de télécharger le rapport est affichée dans le volet **Participants**. Par défaut, ce paramètre n’est pas activé.

Pour empêcher un organisateur de la réunion de télécharger le rapport, définissez le paramètre sur **Désactivé**.

## <a name="meeting-registration"></a>Inscription à une réunion

Il s’agit d’une stratégie par utilisateur. Si vous l’activer, les utilisateurs de votre organisation peuvent configurer des webinaires. Cette stratégie est activée par défaut.

Pour modifier cette stratégie dans le centre Teams’administration, voir **Stratégies**  >  **de réunion.** Pour désactiver l’inscription à une réunion, définissez la stratégie sur **Désactiver.**

Vous pouvez modifier une stratégie de réunion Teams existante à l’aide de l’applet de commande [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour activer l’inscription à une réunion, définissez le **paramètre MeetingRegistration** sur **True.** Cette option est définie par défaut sur **True.**

Pour désactiver l’inscription aux réunions et empêcher les utilisateurs de planifier des webinaires, définissez le paramètre sur **False.**

## <a name="who-can-register"></a>Qui pouvez vous inscrire

Cette stratégie contrôle les utilisateurs qui peuvent s’inscrire et participer à des webinaires. Cette stratégie présente deux options, qui ne sont disponibles que si **l’enregistrement** de réunion est désactivé.

- Définissez **Qui** peuvent s’inscrire à Tout le monde si vous voulez autoriser tout le monde, y compris les utilisateurs anonymes, à s’inscrire et à participer à des webinaires que les utilisateurs de votre organisation ont créés. 
- Définissez Qui peuvent  **s’inscrire** à tous les membres de l’organisation si vous voulez autoriser uniquement les utilisateurs de votre organisation à s’inscrire et à participer à des webinaires.

Par défaut, **la Qui peut s’inscrire** est définie sur **Tout le monde.** Pour modifier cette stratégie dans le centre Teams’administration, voir **Stratégies**  >  **de réunion.**

Vous pouvez modifier une stratégie de réunion Teams existante à l’aide de l’applet de commande [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour autoriser tout le monde, y compris les utilisateurs anonymes, à s’inscrire et à participer à des webinaires, définissez le paramètre **WhoCanRegister** sur **Tout le monde.** Cette option est définie par défaut sur **Tout** le monde.

Pour autoriser uniquement les utilisateurs de votre organisation à s’inscrire et à participer à des webinaires, définissez le paramètre **sur EveryoneInCompany.**

## <a name="meeting-provider-for-islands-mode"></a>Fournisseur de réunion pour le mode Islands

Il s’agit d’une stratégie par utilisateur. Ce paramètre détermine quel complément de réunion Outlook est utilisé pour *les utilisateurs en mode îles*. Vous pouvez spécifier si les utilisateurs peuvent utiliser uniquement le complément réunion Teams ou les deux compléments réunion et Skype® Entreprise pour planifier des réunions dans Outlook.

Vous ne pouvez appliquer cette stratégie uniquement aux utilisateurs qui sont en mode Îles et dont le paramètre **AllowOutlookAddIn** est défini sur **True** dans leur stratégie de réunion Teams.

Pour l’instant, vous pouvez uniquement utiliser PowerShell pour définir cette stratégie. Vous pouvez modifier une stratégie de réunion Teams existante à l’aide de l’applet de commande [CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) . Vous pouvez également créer une stratégie de réunion Teams à l’aide de l’applet de commande [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) et l’affecter à des utilisateurs.

Pour spécifier le complément de la réunion que vous voulez mettre à la disposition des utilisateurs, définissez le paramètre **PreferredMeetingProviderForIslandsMode** comme suit :

- Définir le paramètre sur **TeamsAndSfB** pour activer le complément réunion Teams et Skype® Entreprise dans Outlook. Ceci est la valeur par défaut.
- Définir le paramètre sur **Teams** pour activer uniquement le complément réunion équipes dans Outlook. Ce paramètre de stratégie permet de s’assurer que toutes les réunions ultérieures ont un lien participer à une réunion Teams. Il ne migre pas les liens de jointure de réunion Skype Entreprise existants vers Teams. Ce paramètre de stratégie n’affecte pas les fonctionnalités de présence, de conversation, d’appel RTC ou d’autres fonctionnalités de Skype Entreprise, ce qui signifie que les utilisateurs continueront à utiliser Skype Entreprise pour ces fonctionnalités.

  Si vous avez défini le paramètre sur **Teams**, puis revenez à **TeamsAndSfB**, les deux compléments de réunion sont activés. Cependant, notez que les liens de réunion Teams existants ne seront pas migrés vers Skype Entreprise. Seules les réunions Skype Entreprise planifiées après la modification auront un lien de jointure de réunion Skype Entreprise.

## <a name="meeting-reactions"></a>Réactions aux réunions

Le paramètre AllowMeetingReactions ne peut être appliqué qu’avec PowerShell. Il n’y a pas d’option pour activer ou désactiver AllowMeetingReactions dans le centre d’administration Teams.

Les réactions pendant les réunions sont désactivées par défaut. La désactivation des réactions pour un utilisateur ne signifie pas qu’il ne peut pas utiliser les réactions dans les réunions qu’il planifie. L’organisateur de la réunion peut toujours activer les réactions à partir de la page des options de réunion, quel que soit le paramètre par défaut.


## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies dans Teams](policy-assignment-overview.md)
- [Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs](meeting-policies-restricted-anonymous-access.md)
