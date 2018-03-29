---
title: Suppression d’une configuration d’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Résumé : Découvrez comment supprimer une configuration d’archivage dans Skype pour Business Server 2015.'
ms.openlocfilehash: 810c195f34a729218118744d4b6943e8dd60eb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server-2015"></a>Suppression d’une configuration d’archivage dans Skype Entreprise Server 2015

**Résumé :** Découvrez comment supprimer une configuration d’archivage dans Skype pour Business Server 2015.
  
Vous pouvez supprimer une configuration de site ou une configuration de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Supprimer une configuration d’archivage via le Panneau de configuration

Pour supprimer une configuration d’archivage en utilisant le Panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.
    
    > [!NOTE]
    > Vous pouvez cliquer sur Configuration globale, mais choisir cette option uniquement si vous voulez rétablir les valeurs par défaut de la configuration globale. 
  
5. Cliquez sur **Valider**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Supprimer une configuration d’archivage via Windows PowerShell

Vous pouvez également supprimer une configuration d’archivage à l’aide de l’applet de commande **Remove-CsArchivingConfiguration** .
  
Par exemple, la commande suivante supprime les paramètres de la configuration d’archivage appliquées au site Redmond. Lorsqu’une stratégie configurée au niveau de l’étendue Site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

La commande suivante supprime tous les paramètres de configuration d’archivage appliqués à l’étendue du service :
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

La commande suivante supprime tous les paramètres de configuration d’archivage là où l’archivage Exchange a été désactivé :
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Vous pouvez également utiliser l’applet de commande **Remove-CsArchivingConfiguration** pour rétablir les valeurs par défaut des paramètres globaux. Par exemple, supposons que vous avez activé l’archivage d’une session de messagerie instantanée au niveau global ; la commande suivante rétablit la valeur par défaut None, ce qui désactive l’archivage au niveau global :
  
```
Remove-CsArchivingConfiguration -Identity global
```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .