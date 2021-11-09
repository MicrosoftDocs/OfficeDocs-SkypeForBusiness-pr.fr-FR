---
title: Créer une stratégie d’archivage dans Skype Entreprise Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Résumé : Découvrez comment créer une stratégie d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: d60ca9399681bf44fadcf7767b7be1499e99cb99
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836446"
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
    
   - Pour créer une stratégie d’archivage au niveau du site, cliquez sur Stratégie de **site,** puis, dans Sélectionner un **site,** cliquez sur le site auquel la stratégie doit être appliquée.
    
   - Pour créer une stratégie d’archivage au niveau de l’utilisateur, cliquez sur **Stratégie de l’utilisateur**.
    
5. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie (par exemple, externalContoso).
    
   - Dans **Description**, entrez des informations décrivant la stratégie (par exemple, stratégie d’archivage des utilisateurs externes pour Contoso).
    
   - Pour contrôler l’archivage des communications avec les utilisateurs internes, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
   - Pour contrôler l’archivage des communications avec les utilisateurs externes, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
    > [!IMPORTANT]
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, voir [Appliquer une stratégie d’archivage](apply-a-policy-to-users.md)aux utilisateurs dans Skype Entreprise Server . 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Créer une stratégie d’archivage à l’aide Windows PowerShell

Vous pouvez également créer de nouvelles stratégies d’archivage à l’Windows PowerShell cmdlet **New-CsArchivingPolicy.** Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [New-CsArchivingPolicy.](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)
  
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

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Pour créer une stratégie d’archivage qui active l’archivage des sessions de communication internes

Dans la mesure où aucun paramètre (à l’exception du paramètre obligatoire Identity) n’a été spécifié dans les commandes précédentes, les nouvelles stratégies utilisent les valeurs par défaut pour toutes leurs propriétés. Pour créer des stratégies qui utilisent des valeurs de propriétés distinctes, il vous suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, la commande suivante crée une stratégie d’archivage qui autorise l’archivage des sessions de messagerie instantanée internes : 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Pour créer une stratégie d’archivage qui active l’archivage des sessions de communication internes et externes

Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande configure la nouvelle stratégie pour archiver les sessions de messagerie instantanée internes et externes :
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```