---
title: Créer une stratégie d’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Résumé : Découvrez comment créer une stratégie d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: ffa2821ca4871a0e05d0afe2f162512a60df3897
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392636"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Créer une stratégie d’archivage dans Skype Entreprise Server

**Résumé :** Découvrez comment créer une stratégie d’archivage pour Skype Entreprise Server.
  
Vous pouvez créer de nouvelles stratégies d’archivage à l’aide du Panneau de Windows PowerShell cmdlets.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Créer une stratégie d’archivage à l’aide du Panneau de contrôle

Pour créer une stratégie d’archivage à l’aide du Panneau de contrôle :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes : 
    
   - Pour créer une stratégie d’archivage au niveau du site, cliquez sur Stratégie de **site, puis**, dans Sélectionner un **site**, cliquez sur le site auquel la stratégie doit être appliquée.
    
   - Pour créer une stratégie d’archivage au niveau de l’utilisateur, cliquez sur **Stratégie de l’utilisateur**.
    
5. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie (par exemple, externalContoso).
    
   - Dans **Description**, entrez des informations décrivant la stratégie (par exemple, stratégie d’archivage des utilisateurs externes pour Contoso).
    
   - Pour contrôler l’archivage des communications avec les utilisateurs internes, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications avec les utilisateurs externes, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
    > [!IMPORTANT]
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, voir [Appliquer une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Créer une stratégie d’archivage à l’aide de Windows PowerShell

Vous pouvez également créer de nouvelles stratégies d’archivage à l’Windows PowerShell cmdlet **New-CsArchivingPolicy**. Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Pour créer une stratégie d’archivage au niveau du site

Cette commande crée une stratégie d’archivage pour le site Redmond :
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Pour créer une stratégie d’archivage au niveau de l’utilisateur

Pour créer une stratégie d’archivage au niveau de l’utilisateur, spécifiez simplement une identité unique lors de la création de la stratégie :
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Pour créer une stratégie d’archivage qui permet l’archivage des sessions de communication internes

Dans la mesure où aucun paramètre (à l’exception du paramètre obligatoire Identity) n’a été spécifié dans les commandes précédentes, les nouvelles stratégies utilisent les valeurs par défaut pour toutes leurs propriétés. Pour créer des stratégies qui utilisent des valeurs de propriétés distinctes, il vous suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, la commande suivante crée une stratégie d’archivage qui autorise l’archivage des sessions de messagerie instantanée internes : 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Pour créer une stratégie d’archivage qui permet l’archivage des sessions de communication internes et externes

Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande configure la nouvelle stratégie pour archiver les sessions de messagerie instantanée internes et externes :
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```