---
title: Supprimer une configuration d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Résumé : Découvrez comment supprimer une configuration d’archivage dans Skype Entreprise Server.'
ms.openlocfilehash: f0489fb26526a8e68935754a8689e28eca9ef335
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767882"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Supprimer une configuration d’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment supprimer une configuration d’archivage dans Skype Entreprise Server.
  
Vous pouvez supprimer une configuration de site ou de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, elle est réinitialisée automatiquement aux valeurs par défaut.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Supprimer une configuration d’archivage à l’aide du Panneau de configuration

Pour supprimer une configuration d’archivage à l’aide du Panneau de configuration :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.
    
    > [!NOTE]
    > Vous pouvez également cliquer sur la configuration globale, mais choisissez cette option uniquement si vous souhaitez rétablir les valeurs par défaut de la configuration globale. 
  
5. Cliquez sur **Valider**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Supprimer une configuration d’archivage à l’aide Windows PowerShell

Vous pouvez également supprimer une configuration d’archivage à l’aide de l’cmdlet **Remove-CsArchivingConfiguration.**
  
Par exemple, la commande suivante supprime les paramètres de configuration d’archivage appliqués au site Redmond. Lorsqu’une stratégie configurée au niveau de l’étendue Site est supprimée, les utilisateurs précédemment gérés par la stratégie de site sont automatiquement régis par la stratégie d’archivage globale à la place :
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

La commande suivante supprime tous les paramètres de configuration d’archivage appliqués à l’étendue Service :
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

La commande suivante supprime tous les paramètres de configuration d’archivage pour Exchange’archivage a été désactivé :
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Vous pouvez également utiliser l’cmdlet **Remove-CsArchivingConfiguration** pour rétablir les valeurs par défaut des paramètres globaux. Par exemple, supposons que vous avez activé l’archivage des sessions de messagerie instantanée au niveau global ; La commande suivante réinitialise la valeur par défaut de Aucun, ce qui désactive l’archivage au niveau global :
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsArchivingConfiguration.](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)