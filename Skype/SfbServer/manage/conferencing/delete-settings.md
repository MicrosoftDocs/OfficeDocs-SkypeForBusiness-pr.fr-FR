---
title: Supprimer les paramètres de configuration de la réunion dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Résumé: Découvrez comment supprimer des paramètres de configuration de réunion dans Skype entreprise Server.'
ms.openlocfilehash: a728f1c1de3470cf505163c5cb25996c190e9026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306474"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Supprimer les paramètres de configuration de la réunion dans Skype entreprise Server
 
**Résumé:** Découvrez comment supprimer des paramètres de configuration de réunion dans Skype entreprise Server.
  
Vous pouvez supprimer les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.
  
Vous pouvez supprimer une configuration de site ou d’utilisateur, mais il est impossible de supprimer la configuration globale. Si vous tentez de supprimer la configuration globale, ses valeurs par défaut sont rétablies automatiquement.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Supprimer les paramètres de configuration de la réunion à l’aide du panneau de configuration Skype entreprise Server

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
4. Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool à supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Supprimer les paramètres de configuration de la réunion à l’aide de Skype entreprise Server Management Shell

Pour supprimer les paramètres de réunion, utilisez l’applet de commande **Remove-Cs MeetingConfiguration**.
  
La commande ci-dessous supprime les paramètres de configuration de réunion appliqués au site Redmond :
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

La commande ci-dessous supprime tous les paramètres de configuration de réunion appliqués au niveau du site :
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Pour plus d’informations, y compris une liste complète des paramètres, consultez la rubrique [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

