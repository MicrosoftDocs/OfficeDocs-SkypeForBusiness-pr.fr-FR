---
title: Supprimer des stratégies de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Résumé : Découvrez comment supprimer des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 47138386812ddd401b7aa9edb54f5a619914f6fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847377"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Supprimer des stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment supprimer des stratégies de conférence dans Skype Entreprise Server.
  
Vous pouvez supprimer des stratégies de conférence à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Supprimer des stratégies de conférence à l’aide du Panneau Skype Entreprise Server de conférence

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur Stratégie **de conférence.**
    
4. Dans la liste des stratégies de conférence, cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **Modifier,** puis sur **Supprimer.**
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Supprimer des stratégies de conférence à l’aide Skype Entreprise Server Management Shell

Pour supprimer des stratégies de conférence, utilisez l’cmdlet **Remove-CsConferencingPolicy.**
  
La commande suivante permet de supprimer la stratégie de conférence dont le paramètre Identity a la valeur RedmondConferencingPolicy :
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

La commande suivante supprime toutes les stratégies de conférence qui permettent aux utilisateurs externes d’enregistrer la conférence :
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Pour plus d’informations, notamment sur la syntaxe complète et la liste des paramètres, voir [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
