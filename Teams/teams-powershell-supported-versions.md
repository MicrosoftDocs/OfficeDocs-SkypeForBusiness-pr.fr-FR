---
title: Teams module PowerShell - Versions prise en charge
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez les versions prise en charge du module Teams PowerShell, utilisé pour l’administration de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea8a755c75c5f91c5dbf3a4cd4dd749ac576557c
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63762008"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams module PowerShell - Versions prise en charge

Microsoft Teams versions 4.0.0 ou ultérieures du module PowerShell (TPM) seront les seules versions prise en charge à l’avenir. Toutes les versions antérieures sont sur la voie de la retraite.



## <a name="new-organizations"></a>Nouvelles organisations

À partir du 1er avril 2022, les organisations qui viennent d’Teams pourront utiliser Teams Module PowerShell 4.0.0 ou une date supérieure.



## <a name="current-organizations-non-tpm-active"></a>Organisations actuelles (non TPM actives)

Les organisations qui n’ont pas utilisé la TPM au cours des trois derniers mois (22 janvier au 22 mars) pourront utiliser TPM 4.0.0 ou une valeur supérieure à partir du 1er avril 2022.



## <a name="current-organizations-tpm-active"></a>Organisations actuelles (TPM actives)

Les organisations qui ont utilisé la technologie TPM au cours des trois derniers mois (22 janvier au 22 mars) pourront utiliser la technologie TPM 4.0.0 ou une date supérieure à partir du 15 juin 2022. Nous vous recommandons de mettre à Teams module PowerShell vers la dernière version.


## <a name="important-notes"></a>Notes importantes

- Les notes de publication de toutes Teams versions du module PowerShell sont disponibles Teams notes [de publication PowerShell](teams-powershell-release-notes.md).

- Pour mettre à jour un module PowerShell, vous devez utiliser la même méthode que lors de l’installation du module. Par exemple, si vous utilisiez le module d’installation à l’origine, vous devez utiliser [Update-Module](/powershell/module/powershellget/update-module) pour obtenir la dernière version.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Si vous mettez à Teams jour à partir de la version 1.1.6 du Module PowerShell, mettez à jour vos scripts `Connect-MicrosoftTeams` à utiliser à la place`New-CsOnlineSession`.

-   Lors de la mise à jour, il est suggéré de ne pas utiliser TPM 4.x.x/3.x.x en parallèle avec les versions antérieures à 3.0.0. Par exemple, l’utilisation de la version 4.0.0 & 2.6.0 ensemble pour différentes opérations d’administration dans la même organisation n’est pas recommandée. 

- Modifications connexes
  * Mises à jour Get-CsOnlineUser & Get-CsOnlineVoiceUser dans TPM 3.0.0 et version supérieure : plus d’informations dans [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (publication du Centre de messages – MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Modifications apportées à l’affectation Téléphone de numéro : plus de [détails dans Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Message center post – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>Voir aussi

[Teams notes de publication de PowerShell](teams-powershell-release-notes.md)

[Installer Microsoft Teams PowerShell](teams-powershell-install.md)

[Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams des cmdlet](/powershell/module/teams) 

[Skype Entreprise des cmdlet](/powershell/module/skype) 
