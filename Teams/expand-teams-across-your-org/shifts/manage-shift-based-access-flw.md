---
title: Gérer l’accès par équipe pour les employés en première ligne dans Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment gérer l’accès par équipe dans Teams employés en ligne de votre organisation.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1d8ed8e964d1ffeda8e862992335560c9a6aab
ms.sourcegitcommit: 330b5c3e299ddad5168958e4722d1e0b987372e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2021
ms.locfileid: "53536840"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gérer l’accès par équipe pour les employés en première ligne dans Teams

> [!IMPORTANT]
> Microsoft StaffHub n’existe plus depuis le 30 juin 2020. Nous sommes en train de transformer les fonctionnalités de StaffHub en Microsoft Teams. Aujourd’hui, Teams inclut l’application Plannings pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées à l’avenir. StaffHub a cessé de fonctionner pour tous les utilisateurs le 30 juin 2020. Toute personne qui essaie d’ouvrir StaffHub s’afficher un message lui permettant de télécharger Teams. Pour en savoir plus, consultez l’article [Microsoft StaffHub n’existe plus](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Vue d’ensemble

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La présence dans Microsoft Teams indique la disponibilité et le statut actuel d’un utilisateur pour les autres utilisateurs. La présence des employés en ligne est souvent moins prévisible que les autres employés, car leurs heures de travail ne sont généralement pas les mêmes chaque jour. En tant qu’administrateur, vous pouvez configurer les Teams de manière à afficher un ensemble d’états de présence basés sur shift pour les employés en ligne de votre organisation qui indiquent quand ils sont en déplacement.

Ces signes de présence basés sur un shift sont une coche verte pleine, indiquent Sur shift, Cercle gris avec x, indique Décalage décalé, Cercle rouge plein, indique Occupé(nt) être séparé du jeu d’états de présence par défaut dans &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Avec ces deux ensembles d’états de présence, vous pouvez configurer des expériences différentes pour les membres de votre organisation en fonction de leur rôle.

L’accès basé sur un shift vous permet de gérer l’accès aux employés Teams en dehors des employés en première ligne. Par exemple, vous pouvez configurer Teams pour afficher un message que les employés en ligne doivent prendre en compte avant d’utiliser Teams lorsqu’ils ne sont pas sur un shift programmé.  

## <a name="scenario"></a>Scénario

Voici un exemple de la façon dont votre organisation peut gérer l’accès basé sur des shifts.

Vous avez des employés en ligne de votre organisation qui ne doivent être payés que pendant les heures pendant qui ils travaillent sur un shift que leur responsable a prévu et approuvé. Ils ne doivent pas être payés pour le temps passé à travailler en dehors d’une équipe prévue, ce qui inclut l’utilisation de Teams travail. Vous avez créé un message personnalisé qui indique « Votre temps sur Teams lorsque vous êtes en congé ne sera pas comptabilisé dans le nombre d’heures payables », qui s’affiche lorsque les employés en première ligne essaient d’accéder à Teams en cas d’shift. S’ils choisissent d’Teams,  ils cliquent sur J’accepte, tout en acceptant qu’ils ne seront pas payés pour le moment.

Vous avez également dans votre organisation des travailleurs de l’information qui sont salariés et qui ne travaillent pas en équipe. Vous configurez vos travailleurs de l’information de manière à utiliser les états de présence par défaut dans Teams tout en offrant à vos employés de ligne de garde une présence basée sur shift.

## <a name="shift-based-presence-states"></a>Présence basée sur les shifts

Voici les états de présence en fonction de l’horaire.

|L'application est configurée |L'utilisateur est configuré  |Plus d’informations  |
|---------|---------|---------|
|![Coche vert plein, indique Au shift](../../media/flw-presence-on-shift.png) Sur shift     |         |Définir automatiquement au début d’un shift         |
|![Cercle gris avec x, indique Shift décalé](../../media/flw-presence-off-shift.png) Congé     |         |Définir automatiquement à la fin d’un shift         |
|![Un cercle rouge plein indique Occupé](../../media/flw-presence-busy.png) Occupé      | ![Un cercle rouge plein indique Occupé](../../media/flw-presence-busy.png) Occupé         |Définir automatiquement. Peut également être manuellement définie lorsque le collègue en première ligne est en shift.|

## <a name="off-shift-access-to-teams"></a>Accès par shift à l’Teams

Cette fonctionnalité vous permet de gérer l’accès aux employés Teams les employés en première ligne qui sont en déplacement. Vous pouvez configurer Teams pour afficher un message aux employés de première ligne s’ils accèdent à Teams congés. Les employés en ligne doivent cliquer **sur J’accepte** pour accepter le message avant de pouvoir Teams.

Vous pouvez utiliser le message par défaut, faire votre choix parmi un ensemble de messages prédéfin définis ou personnaliser le message pour afficher le texte de votre choix. Voici le message par défaut :

![Capture d’écran du message par défaut](../../media/shifts-presence-message.png)

Vous pouvez également définir la fréquence d’affichage du message et définir une période de grâce entre le début ou la fin du premier shift et l’accès à Teams est restreint.

## <a name="manage-shift-based-access"></a>Gérer l’accès en fonction des shifts

En tant qu’administrateur, vous utilisez des stratégies pour contrôler la présence basée sur les shifts pour les employés en première ligne de votre organisation. Vous gérez ces stratégies à l’aide des cmdlets PowerShell suivantes :

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Utilisez l'New-CsTeamsShiftsPolicy cmdlet pour créer une stratégie, définissez les paramètres de stratégie de votre souhaitez, puis utilisez l'Grant-CsTeamsShiftsPolicy de cmdlet Grant-CsTeamsShiftsPolicy pour affecter la stratégie aux utilisateurs.

Voici quelques exemples. Pour plus d’informations sur chaque paramètre et paramètre de stratégie, y compris la liste des messages de shift prédéfinie parmi lesquels vous pouvez faire votre choix, consultez [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Exemple 1

Dans cet exemple, nous créons une stratégie nommée Off Shift Teams Access Default Message. Dans cette stratégie, la présence basée sur les shifts est désactivée et le message par défaut s’affiche chaque fois qu’un utilisateur affecté à cette stratégie accède à Teams congé. L’utilisateur peut utiliser Teams lorsqu’il est en congé s’il accepte le message, et la période de grâce entre le début du premier shift ou la fin du dernier shift et lorsque l’accès est restreint est de 10 minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Utilisez le **paramètre ShiftNoticeMessageType** pour définir le message à afficher. Pour consulter la liste des messages prédéfinie parmi ceux que vous pouvez choisir pour ce paramètre, consultez [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Exemple 2 

Dans cet exemple, nous créons une stratégie nommée Off Shift Teams Message personnalisé Access. Dans cette stratégie, la présence basée sur les shifts est désactivée et un message personnalisé s’affiche chaque fois qu’un utilisateur affecté à cette stratégie accède à Teams lorsqu’il est en congé. L’utilisateur peut utiliser Teams lorsqu’il est en congé s’il accepte le message, et la période de grâce entre le début du premier shift ou la fin du dernier shift et quand l’accès est restreint est de 15 minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Utilisez le **paramètre ShiftNoticeMessageType** pour définir le message à afficher. Pour en savoir plus, [voir New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Exemple 3

Dans cet exemple, nous créons une stratégie nommée Off Shift Teams Access Message1. Dans cette stratégie, la présence basée sur les shifts est désactivée et le message prédéféré suivant s’affiche chaque fois qu’un utilisateur affecté à cette stratégie accède à Teams lorsqu’il est en congé.

  « Votre employeur n’autorise ou n’approuve pas l’utilisation de son réseau, de ses applications, de ses systèmes ou de ses outils par des employés non exemptés ou par heure pendant leurs heures non travaillées. En l’acceptant, vous reconnaissez que l’utilisation de Teams pendant un shift n’est pas autorisée et vous ne serez pas rémunéré ». 

L’utilisateur peut utiliser les Teams lorsqu’il accepte le message et la période de grâce entre le début du premier shift ou la fin du dernier shift et quand l’accès est restreint est de trois minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Utilisez le **paramètre ShiftNoticeMessageType** pour définir le message à afficher. Pour consulter la liste des messages prédéfinie parmi ceux que vous pouvez choisir pour ce paramètre, consultez [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Exemple 4

Dans cet exemple, nous affectons une stratégie nommée Off Shift Teams Access Custom Message à un utilisateur nommé remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Sujets associés

- [Gérer l’application Shifts pour votre organisation dans Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Présentation de Teams PowerShell](../../teams-powershell-overview.md)