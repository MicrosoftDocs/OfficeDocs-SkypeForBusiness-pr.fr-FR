---
title: Modifier une stratégie dans Skype d’archivage pour Business Server existante
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Résumé : Découvrez comment modifier l’utilisateur, les stratégies d’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 66365ea489f0450f0489c03bf0e273731d5526a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884335"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Modifier une stratégie dans Skype d’archivage pour Business Server existante
 
**Résumé :** Découvrez comment modifier l’utilisateur, les stratégies d’archivage pour Skype pour Business Server.
  
Lorsque vous déployez tout d’abord Skype pour Business Server, vous définissez des stratégies d’archivage initiales qui déterminent la façon dont l’archivage est implémenté pour les utilisateurs de votre déploiement. Cette rubrique explique comment gérer et modifier des stratégies. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Modifier des options d’archivage via le Panneau de configuration

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **Stratégie d’archivage**.
    
4. Dans la liste des stratégies, effectuez l’une des opérations suivantes : 
    
   - Pour modifier la stratégie pour l’ensemble de votre déploiement, cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
   - Pour modifier la stratégie pour un seul site, cliquez sur le nom du site dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
   - Pour modifier la stratégie pour un seul utilisateur ou groupe d’utilisateurs, cliquez sur l’utilisateur ou le groupe d’utilisateurs dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans la page **Modifier la stratégie d’archivage**, procédez comme suit :
    
   - Pour activer ou désactiver l’archivage interne de la stratégie, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour activer ou désactiver l’archivage externe de la stratégie, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
    > [!IMPORTANT]
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, voir [appliquer une stratégie d’archivage pour les utilisateurs de Skype pour Business Server](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Modifier les stratégies d’archivage via Windows PowerShell

Vous pouvez également modifier les stratégies d’archivage via l’applet de commande **Set-CsArchivingPolicy** de Windows PowerShell.
  
### <a name="enable-archiving-policies"></a>Activer des stratégies d’archivage

Pour activer l’archivage des sessions de communication internes, affectez la valeur True ($True) au paramètre ArchiveInternal : 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Pour activer l’archivage des sessions de communication externes, affectez la valeur True ($True) au paramètre ArchiveExternal : 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Pour activer l’archivage des sessions de communication internes et externes, définissez la valeur des paramètres de la ArchiveInternal et ArchiveExternal sur True : 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Désactiver des stratégies d’archivage

Pour désactiver complètement l’archivage, affectez la valeur False ($False) aux deux propriétés ArchiveInternal et ArchiveExternal : 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
