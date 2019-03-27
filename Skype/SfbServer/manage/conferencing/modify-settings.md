---
title: Modifier les paramètres de configuration dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Résumé : Découvrez comment modifier les paramètres de configuration dans Skype pour Business Server.'
ms.openlocfilehash: 73127bfce04c8c124ce8036222d755de6bc37058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876047"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modifier les paramètres de configuration dans Skype pour Business Server
 
**Résumé :** Découvrez comment modifier les paramètres de configuration dans Skype pour Business Server.
  
Vous pouvez modifier les paramètres de configuration de réunion à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modifier les paramètres de configuration de réunion à l’aide de Skype pour Business Server Control Panel

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2.  Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.
    
4. Dans la liste des configurations de réunion, cliquez sur la configuration à modifier, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.
    
6. Cliquez sur **Valider**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modifier les paramètres de configuration de réunion à l’aide de Skype pour Business Server Management Shell

Pour modifier les paramètres de configuration de réunion, utilisez l’applet de commande ** Set-CsMeetingConfiguration**.
  
La commande de l’exemple ci-dessous modifie les paramètres de configuration de réunion affectés au site Redmond (-Identity site:Redmond). Dans ce cas, la valeur de la propriété DesignateAsPresenter est Everyone :
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Pour plus d’informations, notamment une liste complète des paramètres, voir [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

