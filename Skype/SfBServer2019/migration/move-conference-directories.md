---
title: Déplacement des annuaires de conférences
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférences de votre pool hérité.
ms.openlocfilehash: c3bee8160e7387102f6d45fc39fa821d2f0df161
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298140"
---
# <a name="move-conference-directories"></a>Déplacement des annuaires de conférences

Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire de conférences de votre pool hérité.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Pour déplacer un annuaire de conférences vers Skype entreprise Server 2019

1. Ouvrez Skype entreprise Server Management Shell.
    
2. Pour obtenir l’identité des annuaires de conférences au sein de votre organisation, exécutez la commande suivante:
    
   ```
   Get-CsConferenceDirectory
   ```

    La commande précédente renvoie tous les annuaires de conférences de votre organisation. Pour cette raison, il est possible que vous souhaitiez limiter les résultats au pool en cours de désactivation. Par exemple, si vous désaffectez le pool avec le nom de domaine complet (FQDN) pool01.contoso.net, utilisez cette commande pour limiter les données renvoyées aux annuaires de conférences à partir du pool:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Cette commande renvoie uniquement les répertoires de conférences dans lesquels la propriété ServiceID contient le nom de domaine complet pool01.contoso.net.
    
3. Pour déplacer des répertoires de conférence, exécutez la commande suivante pour chaque annuaire de conférences de la liste:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Par exemple, pour déplacer l’annuaire de conférences 3, utilisez cette commande en spécifiant un pool Skype entreprise Server 2019 en tant que TargetPool:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Si vous souhaitez déplacer tous les répertoires de conférence sur un pool, utilisez une commande similaire à ce qui suit:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Télécharger la désinstallation de l' [ancien et](https://go.microsoft.com/fwlink/p/?linkId=246227) de la suppression de rôles de serveur pour obtenir des instructions complètes et détaillées sur la mise en service des pools hérités.
  
Lorsque vous déplacez des répertoires de conférence, vous pouvez rencontrer l’erreur suivante:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Cette erreur se produit généralement lorsque Skype entreprise Server Management Shell nécessite un ensemble mis à jour d’autorisations Active Directory pour effectuer une tâche. Pour résoudre le problème, fermez l’instance actuelle de Management Shell, puis ouvrez une nouvelle instance de l’interpréteur de commandes, puis réexécutez la commande pour déplacer l’annuaire de conférence.
  

