---
title: Modifier les stratégies de conférence de Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Résumé : Découvrez comment modifier les stratégies de conférence de Skype pour Business Server.'
ms.openlocfilehash: 36b6cb92ddb1a6628186198906da87c5dec29532
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878041"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modifier les stratégies de conférence de Skype pour Business Server
 
**Résumé :** Découvrez comment modifier les stratégies de conférence de Skype pour Business Server.
  
Vous pouvez modifier les stratégies de conférence à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modifier les stratégies de conférence à l’aide de Skype pour Business Server Control Panel

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
4. Dans la liste des stratégies de conférence, cliquez sur la stratégie à modifier, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conférence**, modifiez les paramètres de stratégie, à l’exception du nom de la stratégie qui ne peut pas être modifié.
    
6. Cliquez sur **Valider**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modifier les stratégies de conférence à l’aide de Skype pour Business Server Management Shell

Pour modifier les stratégies de conférence, utilisez l’applet de commande **Set-CsConferencingPolicy** .
  
L’exemple qui suit modifie une valeur de propriété de la stratégie de conférence SalesConferencingPolicy. La commande définit la valeur de la propriété AllowConferenceRecording sur False :
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Pour plus d’informations, y compris la syntaxe complète et une liste des paramètres, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

