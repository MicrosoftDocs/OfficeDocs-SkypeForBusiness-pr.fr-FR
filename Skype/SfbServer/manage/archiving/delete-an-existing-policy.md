---
title: Supprimer une stratégie d’archivage existante dans Skype Entreprise Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Résumé : Découvrez comment supprimer une stratégie d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: 4c660a3143774d0b7db0c5b9cfff3688dd47acdb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767872"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Supprimer une stratégie d’archivage existante dans Skype Entreprise Server

**Résumé :** Découvrez comment supprimer une stratégie d’archivage pour Skype Entreprise Server.
  
Vous pouvez supprimer une stratégie utilisateur ou une stratégie de site, mais pas la stratégie globale. Si vous supprimez la stratégie globale, Skype Entreprise Server réinitialise automatiquement les valeurs par défaut de la stratégie.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Supprimer une stratégie à l’aide du Panneau de contrôle

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Dans la liste des stratégies d’archivage, cliquez sur la stratégie d’utilisateur ou de site à supprimer, cliquez sur **Modifier,** puis sur **Supprimer.**
    
5. Cliquez sur **Valider**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Supprimer une stratégie à l’aide Windows PowerShell

Vous pouvez également supprimer des stratégies d’archivage à l’aide de l’cmdlet **Remove-CsArchivingPolicy.**
  
Par exemple, la commande suivante supprime la stratégie dont l’identité est site:Redmond. Lorsqu’une stratégie configurée au niveau du site est supprimée, les utilisateurs précédemment gérés par la stratégie de site sont automatiquement régis par la stratégie d’archivage globale à la place :
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Cette commande supprime toutes les stratégies d’archivage appliquées au niveau utilisateur :
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Cette commande supprime toutes les stratégies d’archivage pour laquelle l’archivage interne a été désactivé :
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsArchivingPolicy.](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)