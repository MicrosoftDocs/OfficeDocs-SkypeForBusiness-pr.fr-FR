---
title: Supprimer des stratégies de conférence de Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Résumé : Découvrez comment supprimer les stratégies de conférence de Skype pour Business Server.'
ms.openlocfilehash: 404e981af46b29bd95b36ca402c9f691e34737a5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222806"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Supprimer des stratégies de conférence de Skype pour Business Server
 
**Résumé :** Découvrez comment supprimer les stratégies de conférence de Skype pour Business Server.
  
Vous pouvez supprimer des stratégies de conférence à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Supprimer des stratégies de conférence à l’aide de Skype pour Business Server Control Panel

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
4. Dans la liste des stratégies de conférence, cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Supprimer des stratégies de conférence à l’aide de Skype pour Business Server Management Shell

Pour supprimer des stratégies de conférence, utilisez l’applet de commande **Remove-CsConferencingPolicy**.
  
La commande suivante permet de supprimer la stratégie de conférence dont le paramètre Identity a la valeur RedmondConferencingPolicy :
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

La commande ci-dessous permet de supprimer toutes les stratégies de conférence qui autorisent les utilisateurs externes à enregistrer la conférence :
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Pour plus d’informations, y compris la syntaxe complète et une liste des paramètres, voir [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

