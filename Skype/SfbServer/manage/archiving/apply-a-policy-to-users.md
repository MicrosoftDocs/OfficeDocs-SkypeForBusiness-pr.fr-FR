---
title: Appliquer une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Résumé : Découvrez comment affecter une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server.'
ms.openlocfilehash: fadc2d20ce8fb83ef331feb55f5d0908b3189213
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391186"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Appliquer une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server

**Résumé :** Découvrez comment affecter une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server.
  
Si vous avez créé une ou plusieurs stratégies utilisateur pour l’archivage des utilisateurs sur Skype Entreprise Server, vous pouvez implémenter la prise en charge de l’archivage pour des utilisateurs spécifiques en appliquant les stratégies appropriées à ces utilisateurs ou groupes d’utilisateurs. Par exemple, si vous créez une stratégie pour prendre en charge l’archivage des communications internes, vous pouvez l’appliquer à au moins un utilisateur ou groupe d’utilisateurs pour prendre en charge l’archivage des communications Skype Entreprise Server de l’utilisateur.
  
> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de Exchange In-Place Hold contrôlent si l’archivage est activé pour les utilisateurs qui sont Exchange et dont les boîtes aux lettres sont mises en In-Place. Pour plus d’informations, voir [Plan for archiving in Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype Entreprise Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Appliquer une stratégie utilisateur à l’aide du Panneau de contrôle

Pour appliquer une stratégie utilisateur à l’aide du Panneau de contrôle :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer. 
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier l’utilisateur Lync Server sous** stratégie d’archivage **,** sélectionnez la stratégie utilisateur d’archivage à appliquer.
    
    > [!NOTE]
    > Les paramètres **\<Automatic\>** appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Appliquer une stratégie utilisateur à l’aide Windows PowerShell

Vous pouvez également appliquer une stratégie utilisateur à l’aide **Windows PowerShell’une cmdlet Grant-CsArchivingPolicy**.
  
La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Cette commande affecte la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs qui ont des comptes sur le pool de atl-cs-001.contoso.com. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir la documentation de l’cmdlet [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) .
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

La commande suivante supprime toute stratégie d’archivage par utilisateur précédemment attribuée à Ken Myer. Une fois la stratégie par utilisateur supprimée, Ken Myer est automatiquement géré à l’aide de la stratégie globale ou, le cas présent, de sa stratégie de site local. La stratégie de site est prioritaire sur la stratégie globale.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Pour plus d’informations, voir la documentation de l’cmdlet [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
