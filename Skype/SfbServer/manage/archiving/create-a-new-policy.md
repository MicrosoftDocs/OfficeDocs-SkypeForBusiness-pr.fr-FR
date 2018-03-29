---
title: Création d’une stratégie d’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Résumé : Apprenez à créer une nouvelle stratégie d’archivage pour Skype pour Business Server 2015.'
ms.openlocfilehash: 38a87892620a4d4fdd70b2cf855dc37d371b1b57
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server-2015"></a>Création d’une stratégie d’archivage dans Skype Entreprise Server 2015

**Résumé :** Apprenez à créer une nouvelle stratégie d’archivage pour Skype pour Business Server 2015.
  
Vous pouvez créer de nouvelles stratégies d’archivage à l’aide du panneau de configuration ou des applets de commande de Windows PowerShell.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Créer une nouvelle stratégie d’archivage à l’aide du panneau de configuration

Pour créer une nouvelle stratégie d’archivage à l’aide du panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.
    
4. Cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes : 
    
   - Pour créer une stratégie d’archivage au niveau du site, cliquez sur **Stratégie de site**, puis, dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée.
    
   - Pour créer une stratégie d’archivage au niveau de l’utilisateur, cliquez sur **Stratégie de l’utilisateur**.
    
5. Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie (par exemple, externalContoso).
    
   - Dans **Description**, entrez des informations décrivant la stratégie (par exemple, stratégie d’archivage des utilisateurs externes pour Contoso).
    
   - Pour contrôler l’archivage des communications avec les utilisateurs internes, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
  - Pour contrôler l’archivage des communications avec les utilisateurs externes, activez ou désactivez la case à cocher **Archiver les communications externes**.
    
6. Cliquez sur **Valider**.
    
    > [!IMPORTANT]
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, voir [appliquer une stratégie d’archivage pour les utilisateurs de Skype pour Business Server 2015](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Créer une nouvelle stratégie d’archivage à l’aide de Windows PowerShell

Vous pouvez également créer de nouvelles stratégies d’archivage à l’aide de l’applet de commande **New-CsArchivingPolicy** de Windows PowerShell. Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Pour créer une nouvelle stratégie d’archivage au niveau du site :

Cette commande crée une stratégie d’archivage pour le site Redmond :
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Pour créer une nouvelle stratégie d’archivage au niveau de chaque utilisateur :

Pour créer une stratégie d’archivage au niveau de l’étendue Utilisateur, il vous suffit de spécifier une identité unique lors de la création de la stratégie :
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Pour créer une nouvelle stratégie d’archivage qui permet d’archiver des sessions de communication interne

Dans la mesure où aucun paramètre (à l’exception du paramètre obligatoire Identity) n’a été spécifié dans les commandes précédentes, les nouvelles stratégies utilisent les valeurs par défaut pour toutes leurs propriétés. Pour créer des stratégies qui utilisent des valeurs de propriétés distinctes, il vous suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, la commande suivante crée une stratégie d’archivage qui permet l’archivage de sessions de messagerie instantanées internes : 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Pour créer une nouvelle stratégie d’archivage qui permet d’archiver des sessions de communication interne et externe

Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande permet de configurer la nouvelle stratégie visant à archiver les sessions de messagerie instantanée internes et externes :
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```