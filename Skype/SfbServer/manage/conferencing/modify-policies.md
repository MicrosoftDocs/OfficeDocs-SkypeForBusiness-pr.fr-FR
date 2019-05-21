---
title: Modification des stratégies de conférence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Résumé: Découvrez comment modifier les stratégies de conférence dans Skype entreprise Server.'
ms.openlocfilehash: b2c192948f0119a70f031c1c2bbe5de8e776c2f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280410"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modification des stratégies de conférence dans Skype entreprise Server
 
**Résumé:** Découvrez comment modifier les stratégies de conférence dans Skype entreprise Server.
  
Vous pouvez modifier les stratégies de conférence en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modification des stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.
    
4. Dans la liste des stratégies de conférence, cliquez sur la stratégie à modifier, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conférence**, modifiez les paramètres de stratégie, à l’exception du nom de la stratégie qui ne peut pas être modifié.
    
6. Cliquez sur **Valider**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modification des stratégies de conférence à l’aide de Skype entreprise Server Management Shell

Pour modifier les stratégies de conférence, utilisez l’applet **de passe Set-CsConferencingPolicy** .
  
L’exemple qui suit modifie une valeur de propriété de la stratégie de conférence SalesConferencingPolicy. La commande définit la valeur de la propriété AllowConferenceRecording sur False :
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Pour plus d’informations, y compris la syntaxe complète et une liste de paramètres, consultez la rubrique [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

