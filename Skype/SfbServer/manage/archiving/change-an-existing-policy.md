---
title: Modifier une stratégie d’archivage existante dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Résumé : Découvrez comment modifier les stratégies d’archivage des utilisateurs pour Skype Entreprise Server.'
ms.openlocfilehash: b6ddc379f2b5652311be051d47d644a8e2923c1c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854388"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Modifier une stratégie d’archivage existante dans Skype Entreprise Server
 
**Résumé :** Découvrez comment modifier les stratégies d’archivage des utilisateurs Skype Entreprise Server.
  
Lorsque vous déployez Skype Entreprise Server, vous devez configurer des stratégies d’archivage initiales qui déterminent la façon dont l’archivage est implémenté pour les utilisateurs de votre déploiement. Cette rubrique décrit comment gérer et modifier des stratégies. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Modifier les stratégies d’archivage à l’aide du Panneau de contrôle

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Dans la liste des stratégies, effectuez l’une des opérations suivantes : 
    
   - Pour modifier la stratégie pour l’ensemble de votre déploiement, cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
   - Pour modifier la stratégie pour un seul site, cliquez sur le nom du site dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
   - Pour modifier la stratégie pour un seul utilisateur ou groupe d’utilisateurs, cliquez sur l’utilisateur ou le groupe d’utilisateurs dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans la page **Modifier la stratégie d’archivage**, procédez comme suit :
    
   - Pour activer ou désactiver l’archivage interne de la stratégie, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour activer ou désactiver l’archivage externe de la stratégie, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
    > [!IMPORTANT]
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, voir [Appliquer une stratégie d’archivage](apply-a-policy-to-users.md)aux utilisateurs dans Skype Entreprise Server . 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Modifier les stratégies d’archivage à l’aide Windows PowerShell

Vous pouvez également modifier les stratégies d’archivage à l’aide Windows PowerShell cmdlet **Set-CsArchivingPolicy.**
  
### <a name="enable-archiving-policies"></a>Activer les stratégies d’archivage

Pour activer l’archivage des sessions de communication internes, définissez la valeur du paramètre ArchiveInternal sur True ($True) : 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Pour activer l’archivage des sessions de communication externes, définissez la valeur du paramètre ArchiveExternal sur True ($True) : 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Pour activer l’archivage des sessions de communication internes et externes, définissez la valeur des paramètres ArchiveInternal et ArchiveExternal sur True : 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Désactiver les stratégies d’archivage

Pour désactiver complètement l’archivage, définissez la valeur des paramètres ArchiveInternal et ArchiveExternal sur False ($False) : 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
