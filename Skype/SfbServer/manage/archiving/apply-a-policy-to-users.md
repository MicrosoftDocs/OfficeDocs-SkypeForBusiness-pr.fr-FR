---
title: Appliquer une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Résumé : Découvrez comment affecter une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server.'
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817764"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Appliquer une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server

**Résumé :** Découvrez comment affecter une stratégie d’archivage aux utilisateurs dans Skype Entreprise Server.
  
Si vous avez créé une ou plusieurs stratégies utilisateur pour l’archivage pour les utilisateurs de Skype Entreprise Server, vous pouvez implémenter la prise en charge de l’archivage pour des utilisateurs spécifiques en appliquant les stratégies appropriées à ces utilisateurs ou groupes d’utilisateurs. Par exemple, si vous créez une stratégie pour prendre en charge l’archivage des communications internes, vous pouvez l’appliquer à au moins un utilisateur ou groupe d’utilisateurs pour prendre en charge l’archivage des communications Skype Entreprise Server de l’utilisateur.
  
> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive In-Place Exchange contrôlent si l’archivage est activé pour les utilisateurs qui sont homed on Exchange et dont les boîtes aux lettres sont mises en In-Place archive. Pour plus d’informations, voir [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Appliquer une stratégie utilisateur à l’aide du Panneau de contrôle

Pour appliquer une stratégie utilisateur à l’aide du Panneau de contrôle :
  
1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer. 
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier l’utilisateur Lync Server sous** **stratégie** d’archivage, sélectionnez la stratégie utilisateur d’archivage à appliquer.
    
    > [!NOTE]
    > Les **\<Automatic\>** paramètres appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Appliquer une stratégie utilisateur à l’aide de Windows PowerShell

Vous pouvez également appliquer une stratégie utilisateur à l’aide Windows PowerShell l’cmdlet **Grant-CsArchivingPolicy.**
  
La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Cette commande affecte la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs qui ont des comptes sur le pool de atl-cs-001.contoso.com. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir la documentation de l’cmdlet [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

La commande suivante supprime toute stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Une fois la stratégie par utilisateur supprimée, Ken Myer est automatiquement géré à l’aide de la stratégie globale ou, le cas présent, de sa stratégie de site locale. La stratégie de site est prioritaire sur la stratégie globale.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Pour plus d’informations, voir la documentation de l’cmdlet [Grant-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)
  

