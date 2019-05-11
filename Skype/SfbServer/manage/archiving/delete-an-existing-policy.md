---
title: Supprimer une stratégie dans Skype d’archivage pour Business Server existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Résumé : Découvrez comment supprimer une stratégie d’archivage pour Skype pour Business Server.'
ms.openlocfilehash: ca78224b485cb842fe8c794a2975a418239d9583
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885037"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Supprimer une stratégie dans Skype d’archivage pour Business Server existante

**Résumé :** Découvrez comment supprimer une stratégie d’archivage pour Skype pour Business Server.
  
Vous pouvez supprimer une stratégie utilisateur ou une stratégie de site mais la stratégie globale ne peut pas être supprimée. Si vous supprimez la stratégie globale, Skype pour Business Server rétablit automatiquement la stratégie de valeurs par défaut.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Supprimer une stratégie via le Panneau de configuration

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Stratégie d’archivage**.
    
4. Dans la liste des stratégies d’archivage, cliquez sur la stratégie utilisateur ou la stratégie de site que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.
    
5. Cliquez sur **Valider**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Supprimer une stratégie via Windows PowerShell

Vous pouvez également supprimer des stratégies d’archivage via l’applet de commande **Remove-CsArchivingPolicy**.
  
Par exemple, la commande suivante supprime la stratégie avec la syntaxe Identity site:Redmond. Lorsqu’une stratégie configurée au niveau du site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

Cette commande permet de supprimer toutes les stratégies d’archivage appliquées au niveau Utilisateur :
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Cette commande permet de supprimer toutes les stratégies d’archivage où l’archivage interne a été désactivé :
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
