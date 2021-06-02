---
title: Configurer les webinaires dans Microsoft Teams
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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Découvrez comment gérer les stratégies de webinaire pour Teams réunions.
ms.openlocfilehash: aafa7b57eea1228fa5565bb4d5e95304b42751a3
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718045"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>Configurer les webinaires dans Microsoft Teams

Cet article vous aide à configurer votre organisation pour héberger des webinaires.

## <a name="what-are-webinars"></a>Que sont les webinaires ?

Les webinaires sont des réunions structurées où les instructeurs et les participants ont des rôles clairs, souvent utilisés à des fins de formation ou de scénarios de marketing de tête de série.

Après avoir mis en place des webinaires dans votre organisation, vos utilisateurs peuvent planifier des webinaires et ouvrir l’inscription aux participants. Contrairement aux réunions traditionnelles qui incluent de nombreuses discussions et l’affectation de tâches, les webinaires sont destinés aux présentations interactives et fournissent des outils pour l’analyse des participants.

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>Autoriser les utilisateurs à planifier des webinaires à l’aide de PowerShell

Vous pouvez utiliser les attributs suivants dans la cmdlet Windows PowerShell **Set-CsTeamsMeetingPolicy** pour configurer les webinaires dans Teams.

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

Lisez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) pour plus d’informations sur l’cmdlet.

> [!NOTE]
> Avant d’exécuter ces cmdlets, vous devez être connecté à Skype Entreprise PowerShell en ligne. Pour plus d’informations, voir Gérer Skype Entreprise Online avec [Microsoft 365 ou Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

### <a name="allow-users-to-schedule-webinars"></a>Autoriser les utilisateurs à planifier des webinaires

Pour autoriser les utilisateurs de votre organisation à planifier des webinaires, exécutez :

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```
### <a name="configure-who-can-register-for-webinars"></a>Configurer les utilisateurs qui peuvent s’inscrire aux webinaires

Vous pouvez limiter l’inscription aux seuls utilisateurs de votre organisation ou l’ouvrir à tous les utilisateurs à l’intérieur et à l’extérieur de votre client. Par défaut, **WhoCanRegister** est activé et activé sur **Tout le monde.** Si vous voulez désactiver l’inscription aux réunions, définissez **AllowMeetingRegistration** sur **False.**

> [!IMPORTANT]
> N’oubliez **pas que AllowPrivateMeetingScheduling** doit être réglé sur **True** pour que **AllowMeetingRegistration** fonctionne. En outre, les listes Microsoft doivent être définies dans SharePoint. Pour en savoir plus, [consultez les paramètres de contrôle pour les listes Microsoft.](/sharepoint/control-lists)

**Pour autoriser uniquement *les utilisateurs* de votre organisation à s’inscrire aux webinaires, exécutez :**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

Exécutez ensuite :

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**Pour autoriser tout le monde, y compris les utilisateurs anonymes, à s’inscrire aux webinaires, exécutez :**

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

Exécutez ensuite :

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> Si la rejoindre anonyme est désactivée dans les paramètres de réunion, les utilisateurs anonymes ne peuvent pas participer à des webinaires. Pour en savoir plus et activer ce paramètre, consultez [les paramètres de réunion dans Teams.](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>Recueillir la participation aux réunions

Si vous souhaitez que les organisateurs analysent les webinaires inscrits et participé, vous devez activer la stratégie **AllowEngagementReport.** Pour ce faire, exécutez la commande suivante dans PowerShell.

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>Configurer les paramètres de webinaire

Après l’activation de votre environnement pour les webinaires, aucune autre gestion de l’administrateur n’est requise. La stratégie contrôle les options qui s’affichent pour les organisateurs de webinaires.

## <a name="related-topics"></a>Sujets associés

- [Stratégies de réunion dans Teams - Général](meeting-policies-in-teams-general.md)
- [Documentation set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
