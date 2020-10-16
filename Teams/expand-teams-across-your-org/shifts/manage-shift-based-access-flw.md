---
title: Gérer l’accès par Shift pour les travailleurs terrain dans teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment gérer l’accès par Shift dans teams pour les travailleurs de terrain au sein de votre organisation.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01180f95766412b82d9df7986c3667298f24d5b4
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486850"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Gérer l’accès par Shift pour les travailleurs terrain dans teams

> [!IMPORTANT]
> À compter du 30 juin 2020, Microsoft StaffHub a été annulé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub a cessé de fonctionner pour tous les utilisateurs du 30 juin 2020. Tout utilisateur qui tente d’ouvrir StaffHub est affiché un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la section le [retrait de Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Vue d’ensemble

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Dans Microsoft Teams, la présence et l’État actuels d’un utilisateur sont disponibles pour les autres utilisateurs. La présence de travailleurs terrain est souvent moins prévisible par les autres membres du personnel, car leurs heures de travail ne sont généralement pas le même quotidiennement. En tant qu’administrateur, vous pouvez configurer teams pour afficher un ensemble d’États de présence basés sur une équipe pour les travailleurs terrain de votre organisation afin d’indiquer leur date d’ouverture et de fermeture.

Ces États de présence reposant sur une fonction &mdash; ![ de décalage apparaissent sur MAJ ](../../media/flw-presence-on-shift.png) **au**- ![ dessus, avec un cercle gris de x, et indiquent le décalage de décalage ](../../media/flw-presence-off-shift.png) **Off shift** ![ ](../../media/flw-presence-busy.png) **Busy** &mdash; par rapport à l' [ensemble des États de présence](../../presence-admins.md) , Uni/rouge Ces deux jeux de statuts de présence vous permettent de configurer des expériences différentes pour les membres de votre organisation en fonction de leur rôle.

Grâce à l’accès par basculement, vous pouvez gérer l’accès aux équipes lorsque les travailleurs terrain n’ont pas été déplacés. Par exemple, vous pouvez définir teams de sorte qu’il affiche un message indiquant que les utilisateurs de terrain doivent accuser réception avant de pouvoir utiliser teams lorsqu’ils ne sont pas sur une équipe de travail programmée.  

## <a name="scenario"></a>Scénario

Voici un exemple de la façon dont votre organisation peut gérer l’accès par décalage.

Vous avez des travailleurs terrain au sein de votre organisation qui doivent être payés uniquement pendant les heures auxquelles ils travaillent sur une équipe dont le responsable est programmé et approuvé. Ils ne doivent pas être payés pour le temps passé en dehors d’une équipe de travail, y compris l’utilisation de l’application Teams. Vous configurez un message personnalisé indiquant « votre temps sur teams lorsque vous n’êtes pas en voie de décalage par rapport aux heures d’ouverture du compte », qui s’affiche lorsque terrain travailleurs tente d’accéder à teams en cas de non-changement. Si les utilisateurs choisissent d’utiliser Teams, ils peuvent cliquer sur **J’accepte** qu’ils ne seront pas payés pour le moment.

Les travailleurs de votre organisation possèdent également des travailleurs de l’information qui sont salariés et qui ne fonctionnent pas. Vous configurez vos travailleurs de l’information de façon à ce qu’ils utilisent les statuts de présence par défaut dans teams tout en donnant à votre terrain une présence basée sur le changement.

## <a name="shift-based-presence-states"></a>État de présence basée sur une équipe

Voici les statuts de présence basés sur le décalage.

|L'application est configurée |L'utilisateur est configuré  |Plus d’informations  |
|---------|---------|---------|
|![Coche verte unie indiquant sur Shift](../../media/flw-presence-on-shift.png) Sur Maj     |         |Définie automatiquement au début d’une équipe         |
|![Cercle gris avec x, indiquant le décalage](../../media/flw-presence-off-shift.png) Désactiver Maj     |         |Définie automatiquement à la fin d’une équipe         |
|![Un cercle rouge plein indique Occupé](../../media/flw-presence-busy.png) Occupé      | ![Un cercle rouge plein indique Occupé](../../media/flw-presence-busy.png) Occupé         |Définie automatiquement. Peut également être défini manuellement lorsque le travailleur terrain est en déplacement.|

## <a name="off-shift-access-to-teams"></a>Désactiver l’accès en équipe aux équipes

Cette fonctionnalité vous permet de gérer l’accès aux équipes lorsque des travailleurs terrain n’ont pas été déplacés. Vous pouvez définir teams de façon à ce qu’il affiche un message aux travailleurs de terrain s’ils accèdent à teams en cas d’inverser. Les travailleurs terrain doivent cliquer sur **J’accepte** pour accuser réception du message avant de pouvoir utiliser Teams.

Vous pouvez utiliser le message par défaut, faire votre choix parmi un ensemble de messages prédéfinis ou personnaliser le message pour afficher le texte de votre choix. Voici le message par défaut :

![Capture d’écran d’un message par défaut](../../media/shifts-presence-message.png)

Vous pouvez également définir la fréquence lorsque le message est affiché et définir une période de grâce entre la date de début ou la fin de la première Maj et le moment où l’accès aux équipes est limité.

## <a name="manage-shift-based-access"></a>Gérer l’accès par Shift

En tant qu’administrateur, vous utilisez des stratégies pour contrôler la présence basée sur le décalage pour les travailleurs terrain au sein de votre organisation. Pour gérer ces stratégies, utilisez les applets de commande PowerShell suivantes :

- [Nouveau-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Utilisez l’applet de Grant-CsTeamsShiftsPolicy New-CsTeamsShiftsPolicy pour créer une stratégie, définir les paramètres de stratégie de votre choix, puis utiliser l’applet de pour affecter la stratégie aux utilisateurs.

Voici quelques exemples. Pour obtenir des informations détaillées sur chaque paramètre et paramètre de stratégie, y compris la liste de messages de décalage prédéfinis parmi lesquels vous pouvez choisir, voir [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Exemple 1

Dans cet exemple, nous créons une nouvelle stratégie nommée message par défaut à partir de Shift Teams. Dans cette stratégie, la présence basée sur le basculement est activée et le message par défaut s’affiche chaque fois qu’un utilisateur qui est affecté à cette stratégie accède à teams en cas de non-déplacement. L’utilisateur peut utiliser teams en cas de désactivation de la touche Maj s’il accepte le message et la période de grâce entre le début ou la fin de la première Maj et le moment où l’accès est restreint est de 10 minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Utilisez le paramètre **ShiftNoticeMessageType** pour définir le message que vous voulez afficher. Pour afficher une liste des messages prédéfinis à partir desquels vous pouvez faire votre choix pour ce paramètre, voir [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Exemple 2 

Dans cet exemple, nous créons une nouvelle stratégie nommée message personnalisé désactivé. Dans cette stratégie, la présence basée sur le basculement est activée et un message personnalisé s’affiche chaque fois qu’un utilisateur qui dispose de cette stratégie accède à teams lorsque la valeur est désactivée. L’utilisateur peut utiliser teams en cas de désactivation de la touche Maj s’il accepte le message et la période de grâce entre la date de début ou la fin de la première Maj et le moment où l’accès est limité est de 15 minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Utilisez le paramètre **ShiftNoticeMessageType** pour définir le message que vous voulez afficher. Pour en savoir plus, voir [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Exemple 3

Dans cet exemple, nous commençons par créer une nouvelle stratégie appelée Message1. Dans cette stratégie, la présence basée sur le basculement est activée et le message prédéfini suivant est affiché chaque fois qu’un utilisateur qui est affecté à cette stratégie accède à teams lorsque la valeur est désactivée.

  «Votre employeur n’autorise pas l’utilisation de son réseau, de ses applications, de ses systèmes ou de ses outils par des employés non exemptés et des employés à des horaires de travail non exemptés. En acceptant, vous reconnaissez que votre utilisation de teams n’est pas autorisée et que vous ne serez pas indemnisé.» 

L’utilisateur peut utiliser teams en cas de désactivation de la touche Maj s’il accepte le message et la période de grâce entre la date de début ou la fin de la première Maj et la fin de l’accès est 3 minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Utilisez le paramètre **ShiftNoticeMessageType** pour définir le message que vous voulez afficher. Pour afficher une liste des messages prédéfinis à partir desquels vous pouvez faire votre choix pour ce paramètre, voir New-TeamsShiftPolicy.

### <a name="example-4"></a>Exemple 4

Dans cet exemple, nous affectons une stratégie nommée inverser le message personnalisé à un utilisateur appelé remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Voir aussi

- [Gérer l’application Shifts pour votre organisation dans Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Présentation de Teams PowerShell](../../teams-powershell-overview.md)
