---
title: Configurer des webinaires dans Microsoft Teams
ms.author: mabond
author: mkbond007
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
description: Découvrez comment gérer les stratégies de webinaire pour les réunions Teams.
ms.openlocfilehash: 26863b26f960b50d81fa1d98090c3616d5b492a7
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706481"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurer des webinaires dans Microsoft Teams

Cet article vous aidera à configurer votre organisation pour héberger des webinaires.

## <a name="what-are-webinars"></a>Que sont les webinaires ?

Les webinaires sont des réunions structurées où les présentateurs et les participants ont des rôles clairs, souvent utilisés à des fins de formation ou pour des scénarios de génération de prospects commerciaux et marketing.

Après avoir configuré des webinaires dans votre organisation, vos utilisateurs peuvent planifier des webinaires et ouvrir l’inscription aux participants. Contrairement aux réunions traditionnelles qui incluent de nombreuses discussions et affectations de tâches, les webinaires sont destinés à des présentations interactives et fournissent des outils pour l’analyse des participants.

> [!IMPORTANT]
> Pour permettre aux utilisateurs de configurer des webinaires, Listes Microsoft doivent être configurés dans SharePoint en activant la création de listes personnelles. Pour plus d’informations, consultez [Paramètres de contrôle pour Listes Microsoft](/sharepoint/control-lists).

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>Autoriser les utilisateurs à planifier des webinaires dans le Centre d’administration Teams

Vous pouvez utiliser le Centre d’administration Teams pour configurer des webinaires pour votre organisation. Vous trouverez les stratégies permettant de configurer des webinaires dans le Centre d’administration Teams sous Stratégies de **réunion****.** > 

### <a name="meeting-registration"></a>Inscription à la réunion

Si vous activez cette option, les utilisateurs peuvent planifier des webinaires. Par défaut, cette option est activée. Si vous souhaitez désactiver l’inscription à la réunion, définissez cette stratégie sur **Désactivée**.

> [!IMPORTANT]
> **La planification de réunion privée** doit être activée pour que l’inscription à la réunion fonctionne. Par défaut, cette stratégie est activée dans le Centre d’administration Teams. Pour les étudiants des locataires de l’éducation, cette stratégie est désactivée par défaut. Pour plus d’informations sur l’activation de la planification de réunions privées pour les étudiants, consultez [Teams pour l'éducation stratégies et packages de stratégies](policy-packages-edu.md).

### <a name="who-can-register"></a>Qui peut s’inscrire

Si vous sélectionnez **Tout le monde**, tous les utilisateurs, y compris les utilisateurs anonymes, peuvent s’inscrire et participer à des webinaires. Si vous sélectionnez **Tout le monde dans l’organisation**, seuls les utilisateurs de votre organisation peuvent s’inscrire aux webinaires. Si l’inscription à la réunion est désactivée, cette option n’est pas disponible et personne ne peut s’inscrire aux webinaires.

> [!NOTE]
> La valeur par défaut de **Who can register** est **Everyone in the organization** in education tenants. Pour plus d’informations, consultez [Teams pour l'éducation Assistant Stratégie](easy-policy-setup-edu.md).

### <a name="engagement-report"></a>Rapport d’engagement

Lorsque cela est activé, les organisateurs peuvent voir les rapports des personnes inscrites et ayant participé aux webinaires qu’elles ont configurées. Cette stratégie est activée par défaut. Pour plus d’informations, consultez [les stratégies de réunion dans le rapport Teams - Engagement](meeting-policies-in-teams-general.md#engagement-report). Pour plus d’informations sur l’expérience de l’utilisateur final, consultez [Afficher et télécharger les rapports de participation aux réunions](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US).

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Autoriser les utilisateurs à planifier des webinaires à l’aide de PowerShell

Vous pouvez utiliser les attributs suivants dans l’Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** à configurer pour les webinaires dans Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Pour plus d’informations sur l’applet de commande, consultez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) .

> [!NOTE]
> Avant de pouvoir exécuter ces applets de commande, vous devez être connecté à Microsoft Teams PowerShell. Pour plus d’informations, consultez [Gérer Teams avec Microsoft Teams PowerShell](/microsoftteams/teams-powershell-managing-teams).

### <a name="allow-users-to-schedule-webinars"></a>Autoriser les utilisateurs à planifier des webinaires

Vous pouvez limiter l’inscription aux utilisateurs de votre organisation uniquement ou l’ouvrir à tout le monde à l’intérieur et à l’extérieur de votre locataire. Par défaut, **WhoCanRegister** est activé et défini sur **Tout le monde** pour la stratégie **globale (par défaut à l’échelle de l’organisation** ). Si vous souhaitez désactiver l’inscription de réunion, définissez **AllowMeetingRegistration sur** **False**.

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** doit être défini sur **True** pour **que AllowMeetingRegistration** fonctionne.

1. Activer l’inscription à la réunion

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. Activer la planification des réunions privées

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. Configurer qui peut s’inscrire aux webinaires

**Autoriser *uniquement* les utilisateurs de votre organisation à s’inscrire aux webinaires**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Pour permettre à quiconque, y compris aux utilisateurs anonymes, de s’inscrire aux webinaires, exécutez :**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> Si la participation anonyme est désactivée dans les paramètres de réunion, les utilisateurs anonymes ne peuvent pas participer aux webinaires. Pour en savoir plus et activer ce paramètre, consultez [Paramètres de réunion dans Teams](meeting-settings-in-teams.md).

### <a name="collect-meeting-attendance"></a>Collecter la participation aux réunions

Le paramètre **AllowEngagementReport** vous permet de voir qui a inscrit et participé à des webinaires. Cette stratégie est activée par défaut. Pour la désactiver, exécutez la commande suivante dans PowerShell :

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>Configurer les paramètres du webinaire

Après avoir activé votre environnement pour les webinaires, aucune autre gestion d’administration n’est requise. La stratégie contrôle les options qui s’affichent pour les organisateurs de webinaires.

## <a name="related-topics"></a>Rubriques connexes

- [Stratégies de réunion dans Teams - Général](meeting-policies-in-teams-general.md)
- [Documentation Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Assistant Stratégie Teams pour l'éducation](easy-policy-setup-edu.md)
