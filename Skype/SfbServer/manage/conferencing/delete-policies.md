---
title: Supprimer des stratégies de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Résumé : Découvrez comment supprimer des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119503"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Supprimer des stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment supprimer des stratégies de conférence dans Skype Entreprise Server.
  
Vous pouvez supprimer des stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Supprimer des stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Stratégie **de conférence.**
    
4. Dans la liste des stratégies de conférence, cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **Modifier,** puis sur **Supprimer.**
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Supprimer des stratégies de conférence à l’aide de Skype Entreprise Server Management Shell

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
