---
title: Supprimer les paramètres de configuration dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Résumé : Découvrez comment supprimer les paramètres de configuration dans Skype pour Business Server.'
ms.openlocfilehash: 47cde99751c90b71a52b70a0bde9aaf15acf0154
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222757"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Supprimer les paramètres de configuration dans Skype pour Business Server
 
**Résumé :** Découvrez comment supprimer les paramètres de configuration dans Skype pour Business Server.
  
Vous pouvez supprimer les paramètres de configuration de réunion à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.
  
Vous pouvez supprimer une configuration de site ou d’utilisateur, mais il est impossible de supprimer la configuration globale. Si vous tentez de supprimer la configuration globale, ses valeurs par défaut sont rétablies automatiquement.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Supprimer les paramètres de configuration de réunion à l’aide de Skype pour Business Server Control Panel

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
4. Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool à supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Supprimer les paramètres de configuration de réunion à l’aide de Skype pour Business Server Management Shell

Pour supprimer les paramètres de réunion, utilisez l’applet de commande **Remove-Cs MeetingConfiguration**.
  
La commande ci-dessous supprime les paramètres de configuration de réunion appliqués au site Redmond :
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

La commande ci-dessous supprime tous les paramètres de configuration de réunion appliqués au niveau du site :
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Pour plus d’informations, notamment une liste complète des paramètres, voir [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

