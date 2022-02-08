---
title: Supprimer les paramètres de configuration de réunion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: f08869e2cb9c59dc6fb382de6568ad913c329c1a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391126"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Supprimer les paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment supprimer les paramètres de configuration de réunion dans Skype Entreprise Server.
  
Vous pouvez supprimer les paramètres de configuration de réunion à l’Skype Entreprise Server du Panneau de configuration ou Skype Entreprise Server Management Shell.
  
Vous pouvez supprimer une configuration de site ou d’utilisateur, mais vous ne pouvez pas supprimer la configuration globale. Si vous essayez de supprimer la configuration globale, elle est automatiquement réinitialisée aux valeurs par défaut.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Supprimer les paramètres de configuration de réunion à l’aide Skype Entreprise Server panneau de configuration

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
4. Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool à supprimer, cliquez sur **Modifier, puis** sur **Supprimer**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Supprimer les paramètres de configuration de réunion à l’aide Skype Entreprise Server Management Shell

Pour supprimer les paramètres de réunion, utilisez l’cmdlet **Remove-CsMeetingConfiguration** .
  
La commande suivante supprime les paramètres de configuration de réunion appliqués au site Redmond :
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

La commande suivante supprime tous les paramètres de configuration de réunion appliqués à l’étendue Site :
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Pour plus d’informations, y compris une liste complète des paramètres, voir [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
