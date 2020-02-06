---
title: Créer une nouvelle stratégie d’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Résumé : Découvrez comment créer une nouvelle stratégie d’archivage pour Skype entreprise Server.'
ms.openlocfilehash: 4d6590ffdb2263783e89d842acf4ba5460259a35
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819046"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Créer une nouvelle stratégie d’archivage dans Skype entreprise Server

**Résumé :** Découvrez comment créer une nouvelle stratégie d’archivage pour Skype entreprise Server.
  
Vous pouvez créer de nouvelles stratégies d’archivage à l’aide du panneau de configuration ou des applets de commande de Windows PowerShell.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Créer une nouvelle stratégie d’archivage à l’aide du panneau de configuration

Pour créer une nouvelle stratégie d’archivage à l’aide du panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie d’archivage**.
    
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
    > Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie. Pour plus d’informations, reportez-vous [à appliquer une stratégie d’archivage aux utilisateurs de Skype entreprise Server](apply-a-policy-to-users.md). 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Créer une nouvelle stratégie d’archivage à l’aide de Windows PowerShell

Vous pouvez également créer de nouvelles stratégies d’archivage à l’aide de l’applet de commande **New-CsArchivingPolicy** de Windows PowerShell. Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de [nouvelle-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Pour créer une nouvelle stratégie d’archivage au niveau du site :

Cette commande crée une stratégie d’archivage pour le site Redmond :
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Pour créer une nouvelle stratégie d’archivage au niveau de chaque utilisateur :

Pour créer une stratégie d’archivage au niveau de l’étendue Utilisateur, il vous suffit de spécifier une identité unique lors de la création de la stratégie :
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Pour créer une nouvelle stratégie d’archivage qui permet d’archiver des sessions de communication interne

Dans la mesure où aucun paramètre (à l’exception du paramètre obligatoire Identity) n’a été spécifié dans les commandes précédentes, les nouvelles stratégies utilisent les valeurs par défaut pour toutes leurs propriétés. Pour créer des stratégies qui utilisent des valeurs de propriétés distinctes, il vous suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, la commande suivante crée une stratégie d’archivage qui permet l’archivage des sessions de messagerie instantanée internes : 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Pour créer une nouvelle stratégie d’archivage qui permet d’archiver des sessions de communication interne et externe

Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande permet de configurer la nouvelle stratégie visant à archiver les sessions de messagerie instantanée internes et externes :
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
