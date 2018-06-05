---
title: Application d’une stratégie d’archivage pour les utilisateurs de Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Résumé : Découvrez comment attribuer une stratégie d’archivage pour les utilisateurs de Skype pour Business Server 2015.'
ms.openlocfilehash: 0a9b19f6b02daae09f71b1f9933c90bfc86c5e23
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569385"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a>Application d’une stratégie d’archivage pour les utilisateurs de Skype Entreprise Server 2015

**Résumé :** Découvrez comment attribuer une stratégie d’archivage pour les utilisateurs de Skype pour Business Server 2015.
  
Si vous avez créé un ou plusieurs stratégies d’utilisateur pour l’archivage pour les utilisateurs hébergement sur Skype pour Business Server 2015, vous pouvez implémenter la prise en charge d’archivage pour des utilisateurs spécifiques en appliquant les stratégies appropriées pour ces utilisateurs ou de groupes d’utilisateurs. Par exemple, si vous créez une stratégie pour prendre en charge l’archivage des communications internes, vous pouvez l’appliquer au moins un utilisateur ou groupe d’utilisateurs pour prendre en charge l’archivage de Skype l’utilisateur pour les communications Business Server 2015.
  
> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, le contrôle de stratégies de blocage sur Place Exchange si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place. Pour plus d’informations, voir [planifier l’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md) et [configurer l’intégration avec le stockage Exchange pour Skype pour Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Appliquer une stratégie utilisateur via le Panneau de configuration

Pour appliquer une stratégie utilisateur via le Panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer. 
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier l’utilisateur Lync Server** sous **stratégie d’archivage**, sélectionnez la stratégie utilisateur d’archivage que vous souhaitez appliquer.
    
    > [!NOTE]
    > Le ** \<automatique\> ** paramètres s’appliquent les paramètres d’installation de serveur par défaut. Le serveur les applique automatiquement.
  
6. Cliquez sur **Valider**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Appliquer une stratégie utilisateur à l’aide de Windows PowerShell

Vous pouvez également appliquer une stratégie utilisateur à l’aide de l’applet de commande Windows PowerShell **Grant-CsArchivingPolicy** .
  
La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Cette commande affecte la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs dont les comptes sont hébergés sur le pool de serveurs d’inscriptions atl-cs-001.contoso.com. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir la documentation d’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

La commande suivante supprime l’assignation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Pour plus d’informations, voir la documentation d’applet de commande [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

