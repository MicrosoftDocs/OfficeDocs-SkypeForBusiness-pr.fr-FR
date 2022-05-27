---
title: Gérer l’accès par équipe pour les travailleurs de première ligne dans Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment gérer l’accès par équipe dans Teams pour les travailleurs de première ligne de votre organisation.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675216"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gérer l’accès par équipe pour les travailleurs de première ligne dans Teams
## <a name="overview"></a>Présentation

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La présence dans Microsoft Teams indique la disponibilité et l’état actuels d’un utilisateur à d’autres utilisateurs. La présence de travailleurs de première ligne est souvent moins prévisible que les autres employés, car leurs heures de travail ne sont généralement pas les mêmes chaque jour. En tant qu’administrateur, vous pouvez configurer Teams pour afficher un ensemble d’états de présence basés sur les shifts pour les employés de première ligne de votre organisation afin d’indiquer quand ils sont en déplacement ou en congé.

Ces états&mdash;![de présence basés sur un décalage sont une coche vert solide, indiquant le décalage.](../../media/flw-presence-on-shift.png) **Lors de l’équipe**, ![cercle gris avec x, indique Décalage désactivé.](../../media/flw-presence-off-shift.png) **Off shift**( ![Cercle rouge plein) indique que Busy](../../media/flw-presence-busy.png) **Busy**&mdash;est distinct de [l’ensemble par défaut des états de présence](../../presence-admins.md) dans Teams. Avec ces deux ensembles d’états de présence, vous pouvez configurer différentes expériences pour les personnes de votre organisation en fonction de leur rôle.

Avec l’accès par équipe, vous pouvez gérer l’accès à Teams lorsque les travailleurs de première ligne sont hors service. Par exemple, vous pouvez définir Teams pour afficher un message que les employés de première ligne doivent reconnaître avant de pouvoir utiliser Teams lorsqu’ils ne sont pas en équipe planifiée.  

## <a name="scenario"></a>Scénario

Voici un exemple de la façon dont votre organisation peut gérer l’accès en fonction du décalage.

Vous avez des employés de première ligne dans votre organisation qui ne doivent être payés que pour les heures qu’ils travaillent sur un quart que leur responsable a planifié et approuvé. Ils ne doivent pas être payés pour le temps passé à travailler en dehors d’un quart de travail planifié, ce qui inclut l’utilisation de l’application Teams. Vous configurez un message personnalisé indiquant « Votre temps sur Teams en dehors du quart ne comptera pas pour les heures payables », qui s’affiche lorsque les employés de première ligne tentent d’accéder à Teams en dehors du quart de travail. S’ils choisissent d’utiliser Teams, ils cliquent sur **J’accepte** en comprenant qu’ils ne seront pas payés pour cette fois.

Vous avez également des travailleurs de l’information dans votre organisation qui sont salariés et qui ne travaillent pas par quarts de travail. Vous configurez vos travailleurs de l’information de manière à utiliser les états de présence par défaut dans Teams tout en offrant à vos employés de première ligne une présence basée sur des équipes.

## <a name="shift-based-presence-states"></a>États de présence basés sur un décalage

Voici les états de présence basés sur un décalage.

|L'application est configurée |L'utilisateur est configuré  |Plus d’informations  |
|---------|---------|---------|
|![Coche verte unie, indique En équipe.](../../media/flw-presence-on-shift.png) En quart de travail     |         |Définir automatiquement au début d’un quart de travail         |
|![Cercle gris avec x, indique Décalage désactivé](../../media/flw-presence-off-shift.png) Décalage désactivé     |         |Définir automatiquement à la fin d’un décalage         |
|![Un cercle rouge plein indique Occupé](../../media/flw-presence-busy.png) Occupé      | ![Un cercle rouge plein indique Occupé](../../media/flw-presence-busy.png) Occupé         |Défini automatiquement. Peut également être défini manuellement lorsque le travailleur de première ligne est en équipe.|

## <a name="off-shift-access-to-teams"></a>Désactiver l’accès par décalage à Teams

Cette fonctionnalité vous permet de gérer l’accès aux Teams lorsque les employés de première ligne sont hors poste. Vous pouvez définir Teams pour afficher un message aux travailleurs de première ligne s’ils accèdent à Teams lorsqu’ils sont hors équipe. Les employés de première ligne doivent cliquer sur **J’accepte** pour accepter le message avant de pouvoir utiliser Teams.

Vous pouvez utiliser le message par défaut, choisir parmi un ensemble de messages prédéfinis ou personnaliser le message pour afficher le texte souhaité. Voici le message par défaut :

![Capture d’écran du message par défaut.](../../media/shifts-presence-message.png)

Vous pouvez également définir la fréquence à laquelle le message s’affiche et définir une période de grâce entre le début du premier décalage ou la fin du dernier décalage et le moment où l’accès à Teams est restreint.

## <a name="manage-shift-based-access"></a>Gérer l’accès en fonction du décalage

En tant qu’administrateur, vous utilisez des stratégies pour contrôler la présence basée sur les décalages pour les employés de première ligne de votre organisation. Vous gérez ces stratégies à l’aide des applets de commande PowerShell suivantes :

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Utilisez l’applet de commande New-CsTeamsShiftsPolicy pour créer une stratégie, définissez les paramètres de stratégie souhaités, puis utilisez l’applet de commande Grant-CsTeamsShiftsPolicy pour affecter la stratégie aux utilisateurs.

Voici quelques exemples. Pour plus d’informations sur chaque paramètre et paramètre de stratégie, y compris la liste des messages de décalage prédéfinis parmi lesquels vous pouvez choisir, consultez [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Exemple 1

Dans cet exemple, nous créons une stratégie nommée Off Shift Teams Access Default Message. Dans cette stratégie, la présence basée sur un décalage est activée et le message par défaut s’affiche chaque fois qu’un utilisateur auquel cette stratégie est affectée accède Teams en cas de décalage. L’utilisateur peut utiliser Teams en cas de décalage s’il accepte le message, et la période de grâce entre le début du premier décalage ou la fin du dernier quart de travail et le moment où l’accès est restreint est de 10 minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Utilisez le paramètre **ShiftNoticeMessageType** pour définir le message que vous souhaitez afficher. Pour afficher la liste des messages prédéfinis parmi lesquels vous pouvez choisir pour ce paramètre, consultez [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Exemple 2 

Dans cet exemple, nous créons une stratégie nommée Off Shift Teams Access Custom Message. Dans cette stratégie, la présence basée sur un décalage est activée et un message personnalisé s’affiche chaque fois qu’un utilisateur auquel cette stratégie est affectée accède à Teams en cas de décalage. L’utilisateur peut utiliser Teams en cas de décalage s’il accepte le message, et la période de grâce entre le début du premier décalage ou la fin du dernier quart de travail et le moment où l’accès est restreint est de 15 minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Utilisez le paramètre **ShiftNoticeMessageType** pour définir le message que vous souhaitez afficher. Pour en savoir plus, consultez [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Exemple 3

Dans cet exemple, nous créons une stratégie nommée Off Shift Teams Access Message1. Dans cette stratégie, la présence basée sur un décalage est activée et le message prédéfini suivant s’affiche chaque fois qu’un utilisateur auquel cette stratégie est affectée accède à Teams en cas de décalage.

  « Votre employeur n’autorise pas ou n’approuve pas l’utilisation de son réseau, de ses applications, de ses systèmes ou de ses outils par des employés non exemptés ou horaires pendant leurs heures de travail. En acceptant, vous reconnaissez que votre utilisation de Teams pendant le congé n’est pas autorisée et que vous ne serez pas indemnisé. 

L’utilisateur peut utiliser Teams en cas de décalage s’il accepte le message, et la période de grâce entre le début du premier décalage ou la fin du dernier quart de travail et le moment où l’accès est restreint est de trois minutes.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Utilisez le paramètre **ShiftNoticeMessageType** pour définir le message que vous souhaitez afficher. Pour afficher la liste des messages prédéfinis parmi lesquels vous pouvez choisir pour ce paramètre, consultez [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Exemple 4

Dans cet exemple, nous affectons une stratégie nommée Off Shift Teams Access Custom Message à un utilisateur nommé remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Voir aussi

- [Gérer l’application Shifts pour votre organisation dans Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Présentation de Teams PowerShell](../../teams-powershell-overview.md)