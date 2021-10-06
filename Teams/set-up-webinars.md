---
title: Configurer des webinaires dans Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Découvrez comment gérer les stratégies de webinaire pour Teams réunions.
ms.openlocfilehash: 35c0cc2ab6c05d123aae45bc0c375cf815db36b4
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138210"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurer des webinaires dans Microsoft Teams

Cet article vous aide à configurer votre organisation pour héberger des webinaires.

## <a name="what-are-webinars"></a>Que sont les webinaires ?

Les webinaires sont des réunions structurées où les présentateurs et participants ont des rôles clairs, souvent utilisés à des fins de formation ou de scénarios de marketing de tête de série.

Après avoir mis en place des webinaires dans votre organisation, vos utilisateurs peuvent planifier des webinaires et ouvrir l’inscription aux participants. Contrairement aux réunions traditionnelles qui incluent de nombreuses discussions et l’affectation de tâches, les webinaires sont destinés aux présentations interactives et offrent des outils pour l’analyse des participants.

> [!IMPORTANT]
> Pour permettre aux utilisateurs de configurer des webinaires, les Listes Microsoft doivent être configurés dans SharePoint en activant la création de listes personnelles. Pour en savoir plus, [consultez les paramètres de contrôle pour Listes Microsoft.](/sharepoint/control-lists)

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Autoriser les utilisateurs à planifier des webinaires dans le Centre Teams’administration

Vous pouvez utiliser le Centre Teams d’administration pour configurer des webinaires pour votre organisation. Les stratégies de configurer des webinaires se trouvent dans le Centre d’administration Teams sous **Stratégies**  >  **de réunion.**

### <a name="allow-meeting-registration"></a>Autoriser l’inscription à une réunion

Si vous l’activer, les utilisateurs peuvent planifier des webinaires. Par défaut, cette option est désactivée. Si vous souhaitez désactiver l’inscription aux réunions, définissez cette stratégie sur **Désactiver.**

> [!IMPORTANT]
> **Pour que l’enregistrement de** réunion fonctionne, vous devez autoriser la planification de réunions privées. Par défaut, cette stratégie est Teams centre d’administration. Pour les étudiants des locataires Éducation, cette stratégie est désactivée par défaut. Pour plus d’informations sur la façon d’activer la planification de réunions privées pour les étudiants, voir Teams pour l'éducation [stratégies et packages de stratégie.](policy-packages-edu.md)

### <a name="who-can-register"></a>Qui pouvez vous inscrire

Si vous sélectionnez **Tout** le monde, tous les utilisateurs, y compris les utilisateurs anonymes, peuvent s’inscrire et participer à des webinaires. Si vous sélectionnez **Tous les membres de l’organisation,** seuls les utilisateurs de votre organisation peuvent s’inscrire aux webinaires. Si l’inscription à une réunion est désactivée, cette option n’est pas disponible et personne ne peut s’inscrire aux webinaires.

> [!NOTE]
> La valeur par défaut Qui **peut s’inscrire** est Toute personne de **l’organisation** dans les locataires Éducation. Pour plus d’informations, voir [Teams pour l'éducation Assistant Stratégie.](easy-policy-setup-edu.md)

### <a name="allow-engagement-report"></a>Autoriser le rapport d’engagement

Si vous définissez cette fonction, les organisateurs peuvent voir des rapports sur l’inscription et la participation aux webinaires qu’ils ont créés. Cette stratégie est off par défaut. Pour plus d’informations, voir Stratégies de [réunion dans Teams - Autoriser le rapport d’engagement.](meeting-policies-in-teams-general.md#allow-engagement-report) Pour plus d’informations sur l’expérience utilisateur final, voir Afficher et télécharger les rapports de présence [aux réunions.](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Autoriser les utilisateurs à planifier des webinaires à l’aide de PowerShell

Vous pouvez utiliser les attributs suivants dans la cmdlet Windows PowerShell **Set-CsTeamsMeetingPolicy** pour configurer les webinaires dans Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Lisez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) pour plus d’informations sur l’cmdlet.

> [!NOTE]
> Avant d’exécuter ces cmdlets, vous devez être connecté à Microsoft Teams PowerShell. Pour plus d’informations, voir [Gérer Teams avec Microsoft Teams PowerShell.](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>Autoriser les utilisateurs à planifier des webinaires

Vous pouvez limiter l’inscription aux seuls utilisateurs de votre organisation ou l’ouvrir à tous les utilisateurs à l’intérieur et à l’extérieur de votre client. Par défaut, **WhoCanRegister** est activé et activé sur **Tout** le monde pour la stratégie **Globale (à** l’échelle de l’organisation par défaut). Si vous voulez désactiver l’inscription à une réunion, définissez **AllowMeetingRegistration** sur **False.**

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** doit être réglé sur **True** pour que **AllowMeetingRegistration** fonctionne.

1. Activer l’inscription aux réunions

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Activer la planification de réunions privées

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Configurer les utilisateurs qui peuvent s’inscrire aux webinaires

**Autoriser *uniquement les* utilisateurs de votre organisation à s’inscrire aux webinaires**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Pour autoriser tout le monde, y compris les utilisateurs anonymes, à s’inscrire aux webinaires, exécutez :**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Si la rejoindre anonyme est désactivée dans les paramètres de réunion, les utilisateurs anonymes ne peuvent pas participer à des webinaires. Pour en savoir plus et activer ce paramètre, consultez [les paramètres de réunion dans Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>Recueillir la présence à des réunions

Si vous souhaitez que les organisateurs analysent les webinaires inscrits et participé, vous devez activer la stratégie **AllowEngagementReport.** Pour ce faire, exécutez la commande suivante dans PowerShell.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

## <a name="configure-webinar-settings"></a>Configurer les paramètres de webinaire

Après l’activation de votre environnement pour les webinaires, aucune autre gestion de l’administrateur n’est requise. La stratégie contrôle les options qui s’affichent pour les organisateurs de webinaires.

## <a name="related-topics"></a>Sujets associés

- [Stratégies de réunion dans Teams - Général](meeting-policies-in-teams-general.md)
- [Documentation set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams pour l'éducation Assistant Stratégie](easy-policy-setup-edu.md)
