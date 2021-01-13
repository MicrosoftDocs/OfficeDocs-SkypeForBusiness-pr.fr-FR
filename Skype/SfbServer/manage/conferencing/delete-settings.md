---
title: Supprimer les paramètres de configuration de réunion dans Skype Entreprise Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828178"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Supprimer les paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment supprimer les paramètres de configuration de réunion dans Skype Entreprise Server.
  
Vous pouvez supprimer les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
Vous pouvez supprimer une configuration de site ou d’utilisateur, mais vous ne pouvez pas supprimer la configuration globale. Si vous essayez de supprimer la configuration globale, elle est automatiquement réinitialisée aux valeurs par défaut.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Supprimer les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur **Configuration de la réunion.**
    
4. Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool à supprimer, cliquez sur **Modifier,** puis cliquez sur **Supprimer.**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Supprimer les paramètres de configuration de réunion à l’aide de Skype Entreprise Server Management Shell

Pour supprimer les paramètres de réunion, utilisez l’cmdlet **Remove-CsMeetingConfiguration.**
  
La commande suivante supprime les paramètres de configuration de réunion appliqués au site Redmond :
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

La commande suivante supprime tous les paramètres de configuration de réunion appliqués à l’étendue Site :
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Pour plus d’informations, y compris une liste complète des paramètres, voir [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

