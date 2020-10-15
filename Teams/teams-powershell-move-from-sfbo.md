---
title: Basculer entre le connecteur Skype entreprise Online et le module PowerShell teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer du connecteur Skype entreprise Online au module PowerShell teams pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469665"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Basculer entre le connecteur Skype entreprise Online et le module PowerShell teams

Pour passer de l’utilisation du connecteur Skype entreprise Online au module PowerShell teams pour gérer Teams, vous devez mettre à jour vos scripts PowerShell existants. Cet article explique comment procéder.

1. Installez le dernier module PowerShell Teams. Pour connaître les étapes à suivre, voir [installer Microsoft teams PowerShell](teams-powershell-install.md).
2. Désinstaller un connecteur Skype entreprise online. Pour ce faire, dans le panneau de configuration, accédez à **programmes et fonctionnalités**, sélectionnez **Skype entreprise Online, module Windows PowerShell**, puis **désinstaller**. 
3. Dans vos scripts PowerShell, modifiez le nom du module référencé dans ```Import-Module``` ```SkypeOnlineConnector``` ou ```LyncOnlineConnector``` à ```MicrosoftTeams``` .

    Par exemple, remplacez ```Import-Module -Name SkypeOnlineConnector``` par ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Les administrateurs doivent continuer à utiliser [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) et importer la session avant d’utiliser les applets de applet Skype entreprise online. 

## <a name="related-topics"></a>Rubriques connexes

[Installer Microsoft teams PowerShell](teams-powershell-install.md)

[Gestion des équipes avec PowerShell teams](teams-powershell-managing-teams.md)

[Notes de publication teams PowerShell](teams-powershell-release-notes.md)

[Référence sur les applets de passe Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence sur les applets de fonction Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
