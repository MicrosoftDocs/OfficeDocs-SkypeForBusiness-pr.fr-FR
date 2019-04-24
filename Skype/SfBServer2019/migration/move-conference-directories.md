---
title: Déplacement des annuaires de conférences
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences dans votre pool hérité.
ms.openlocfilehash: 32ebe22c54585a206c90888238d96e41fce30a58
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231601"
---
# <a name="move-conference-directories"></a>Déplacement des annuaires de conférences

Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences dans votre pool hérité.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Pour déplacer un annuaire des conférences vers Skype pour Business Server 2019

1. Ouvrez le Skype pour Business Server Management Shell.
    
2. Pour obtenir l’identité des annuaires de conférence dans votre organisation, exécutez la commande suivante :
    
   ```
   Get-CsConferenceDirectory
   ```

    La commande précédente renvoie tous les annuaires des conférences dans votre organisation. Pour cette raison, vous voudrez limiter les résultats vers le pool est désactivé. Par exemple, si vous mettez hors service le pool avec la pool01.contoso.net (FQDN) de nom de domaine complet, utilisez cette commande pour limiter les données renvoyées dans les répertoires de conférence à partir de ce pool :
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Cette commande renvoie uniquement les annuaires des conférences où la propriété ServiceID contient le FQDN pool01.contoso.net.
    
3. Pour déplacer les annuaires des conférences, exécutez la commande suivante pour chaque annuaire des conférences dans le pool :
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Par exemple, pour déplacer un annuaire des conférences 3, utilisez cette commande, en spécifiant un Skype pour Business Server 2019 pool comme le TargetPool :
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Si vous souhaitez déplacer tous les annuaires de conférence sur un pool, utilisez une commande semblable à ce qui suit :
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Télécharger [Microsoft désinstallation hérité et suppression de rôles de serveur](https://go.microsoft.com/fwlink/p/?linkId=246227) pour des instructions détaillées sur la mise hors service des pools hérités complètes.
  
Lors du déplacement des annuaires des conférences, vous pouvez rencontrer l’erreur suivante :
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Cette erreur se produit généralement lorsque le Skype pour Business Server Management Shell nécessite un ensemble d’autorisations Active Directory pour pouvoir exécuter une tâche de mise à jour. Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance de l’interpréteur de commandes et réexécutez la commande pour déplacer l’annuaire des conférences.
  

