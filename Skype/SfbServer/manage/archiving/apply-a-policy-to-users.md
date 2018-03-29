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
description: 'Résumé : Apprenez à affecter une stratégie d’archivage pour les utilisateurs de Skype pour Business Server 2015.'
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a>Application d’une stratégie d’archivage pour les utilisateurs de Skype Entreprise Server 2015

**Résumé :** Découvrez comment affecter une stratégie d’archivage pour les utilisateurs de Skype pour Business Server 2015.
  
Si vous avez créé une ou plusieurs stratégies d’utilisateurs pour l’archivage pour les utilisateurs hébergement sur Skype pour Business Server 2015, vous pouvez implémenter une prise en charge d’archivage pour des utilisateurs spécifiques en appliquant des stratégies appropriées aux utilisateurs ou les groupes d’utilisateurs. Par exemple, si vous créez une stratégie pour prendre en charge l’archivage des communications internes, vous pouvez l’appliquer au moins un utilisateur ou groupe d’utilisateurs pour prendre en charge l’archivage de Skype de l’utilisateur pour les communications d’entreprise serveur 2015.
  
> [!NOTE]
> Si vous activé l’intégration de Microsoft Exchange pour votre déploiement, maintenez la touche Exchange Place le contrôle les stratégies si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange et que leurs boîtes aux lettres sur Place maintenez. Pour plus d’informations, consultez [planification d’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md) et [configurer une intégration avec le stockage Exchange pour Skype pour Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Appliquer une stratégie utilisateur via le Panneau de configuration

Pour appliquer une stratégie utilisateur via le Panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer. 
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. **Modifier l’utilisateur Lync Server** sous **les stratégies d’archivage**, sélectionnez la stratégie d’archivage de l’utilisateur que vous souhaitez appliquer.
    
    > [!NOTE]
    > La ** \<automatique\> ** les paramètres s’appliquent les paramètres d’installation de serveur par défaut. Le serveur les applique automatiquement.
  
6. Cliquez sur **Valider**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Appliquer une stratégie d’utilisateur à l’aide de Windows PowerShell

Vous pouvez également appliquer une stratégie d’utilisateur à l’aide de l’applet de commande Windows PowerShell **Grant-CsArchivingPolicy** .
  
La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Cette commande attribue à l’utilisateur par l’archivage RedmondArchivingPolicy de stratégie à tous les utilisateurs qui ont les comptes hébergés sur le pool Registrar atl-cs-001.contoso.com. Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation d’applet de commande [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

La commande suivante supprime l’assignation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Pour plus d’informations, consultez la documentation d’applet de commande de [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

