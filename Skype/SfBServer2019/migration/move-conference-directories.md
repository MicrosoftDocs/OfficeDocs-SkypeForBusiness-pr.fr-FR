---
title: Déplacement des annuaires de conférences
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences de votre pool hérité.
ms.openlocfilehash: 7e124a81b8aed561419e5965c930ad64988c122540df6660ae68006fe6af9a55
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313852"
---
# <a name="move-conference-directories"></a>Déplacement des annuaires de conférences

Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences de votre pool hérité.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Pour déplacer un annuaire des conférences vers Skype Entreprise Server 2019

1. Ouvrez l Skype Entreprise Server Management Shell.
    
2. Pour obtenir l’identité des annuaires des conférences de votre organisation, exécutez la commande suivante :
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    La commande précédente retourne tous les annuaires des conférences de votre organisation. Pour cette raison, vous pouvez limiter les résultats au pool en cours de désaffectation. Par exemple, si vous désaffectez le pool avec le nom de domaine complet (FQDN) pool01.contoso.net, utilisez cette commande pour limiter les données retournées aux annuaires des conférences de ce pool :
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Cette commande renvoie uniquement les annuaires des conférences dont la propriété ServiceID contient le pool01.contoso.net.
    
3. Pour déplacer les annuaires des conférences, exécutez la commande suivante pour chaque annuaire des conférences du pool :
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Par exemple, pour déplacer l’annuaire des conférences 3, utilisez cette commande, en spécifiant un pool Skype Entreprise Server 2019 en tant que TargetPool :
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Si vous souhaitez déplacer tous les annuaires des conférences sur un pool, utilisez une commande semblable à celle-ci :
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Téléchargez [la désinstallation](https://go.microsoft.com/fwlink/p/?linkId=246227) des rôles serveur hérités et supprimés de Microsoft pour obtenir des instructions détaillées détaillées sur la désaffectation des pools hérités.
  
Lors du déplacement des annuaires des conférences, vous pouvez rencontrer l’erreur suivante :
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Cette erreur se produit généralement lorsque l’Skype Entreprise Server Management Shell requiert un ensemble mis à jour d’autorisations Active Directory pour effectuer une tâche. Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance de l’shell et ré-exécutez la commande pour déplacer l’annuaire des conférences.
  

