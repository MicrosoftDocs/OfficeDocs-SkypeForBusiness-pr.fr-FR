---
title: Suppression d’une configuration de l’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Résumé : Découvrez comment supprimer une configuration d’archivage dans Skype entreprise Server.'
ms.openlocfilehash: 22da9464a4bb6b17c6d4b9aa63ad8990a9152c38
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992371"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Suppression d’une configuration de l’archivage dans Skype entreprise Server

**Résumé :** Découvrez comment supprimer une configuration d’archivage dans Skype entreprise Server.
  
Vous pouvez supprimer une configuration de site ou une configuration de pool, mais vous ne pouvez pas supprimer la configuration globale. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Supprimer une configuration d’archivage via le Panneau de configuration

Pour supprimer une configuration d’archivage en utilisant le Panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
4. Dans la liste des configurations d’archivage, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.
    
    > [!NOTE]
    > Vous pouvez cliquer sur Configuration globale, mais choisir cette option uniquement si vous voulez rétablir les valeurs par défaut de la configuration globale. 
  
5. Cliquez sur **Valider**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Supprimer une configuration d’archivage via Windows PowerShell

Vous pouvez également supprimer une configuration de l’archivage à l’aide de l’applet de passe **Remove-CsArchivingConfiguration** .
  
Par exemple, la commande suivante supprime les paramètres de la configuration d’archivage appliquées au site Redmond. Lorsqu’une stratégie configurée au niveau de l’étendue Site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

La commande suivante supprime tous les paramètres de configuration d’archivage appliqués à l’étendue du service :
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

La commande suivante supprime tous les paramètres de configuration d’archivage là où l’archivage Exchange a été désactivé :
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Vous pouvez également utiliser l’applet de commande **Remove-CsArchivingConfiguration** pour rétablir les valeurs par défaut des paramètres globaux. Par exemple, supposons que vous avez activé l’archivage d’une session de messagerie instantanée au niveau global ; la commande suivante rétablit la valeur par défaut None, ce qui désactive l’archivage au niveau global :
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .
