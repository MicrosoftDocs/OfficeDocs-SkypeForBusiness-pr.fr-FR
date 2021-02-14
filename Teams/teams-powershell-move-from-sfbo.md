---
title: Passer de Skype Entreprise Online Connector au module Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer de Skype Entreprise Online Connector au module Teams PowerShell pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469665"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Passer de Skype Entreprise Online Connector au module Teams PowerShell

Pour passer de l’utilisation de Skype Entreprise Online Connector au module Teams PowerShell afin de gérer Teams, vous devez mettre à jour vos scripts PowerShell existants. Cet article explique comment faire.

1. Installez le module Teams PowerShell le plus récent. Pour consulter la procédure, [voir Installer Microsoft Teams PowerShell.](teams-powershell-install.md)
2. Désinstallez Skype Entreprise Online Connector. Pour ce faire, dans le Panneau de contrôle, sélectionnez Programmes et fonctionnalités, Skype Entreprise **Online, Windows PowerShell Module,** puis **Désinstaller.** 
3. Dans vos scripts PowerShell, modifiez le nom du module référencé. ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams```

    Par exemple, ```Import-Module -Name SkypeOnlineConnector``` changez pour ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Les administrateurs doivent continuer à utiliser [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) et à importer la session avant d’utiliser les cmdlets Skype Entreprise Online. 

## <a name="related-topics"></a>Sujets associés

[Installer Microsoft Teams PowerShell](teams-powershell-install.md)

[Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Référence de l’cmdlet Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence de l’cmdlet Skype Entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
