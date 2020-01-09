---
title: Supprimer une stratégie d’archivage existante dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Résumé : Découvrez comment supprimer une stratégie d’archivage pour Skype entreprise Server.'
ms.openlocfilehash: c08b76996b3d54e8be07e731faae87dce0470cc1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992361"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Supprimer une stratégie d’archivage existante dans Skype entreprise Server

**Résumé :** Découvrez comment supprimer une stratégie d’archivage de Skype entreprise Server.
  
Vous pouvez supprimer une stratégie utilisateur ou une stratégie de site mais la stratégie globale ne peut pas être supprimée. Si vous supprimez la politique globale, Skype entreprise Server réinitialise automatiquement la stratégie aux valeurs par défaut.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Supprimer une stratégie via le Panneau de configuration

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie d’archivage**.
    
4. Dans la liste des stratégies d’archivage, cliquez sur la stratégie utilisateur ou la stratégie de site que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.
    
5. Cliquez sur **Valider**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Supprimer une stratégie via Windows PowerShell

Vous pouvez également supprimer des stratégies d’archivage via l’applet de commande **Remove-CsArchivingPolicy**.
  
Par exemple, la commande suivante supprime la stratégie avec la syntaxe Identity site:Redmond. Lorsqu’une stratégie configurée au niveau du site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Cette commande permet de supprimer toutes les stratégies d’archivage appliquées au niveau Utilisateur :
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Cette commande permet de supprimer toutes les stratégies d’archivage où l’archivage interne a été désactivé :
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
