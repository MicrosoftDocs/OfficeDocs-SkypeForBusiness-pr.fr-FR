---
title: Appliquer une stratégie d’archivage aux utilisateurs de Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Résumé : Découvrez comment attribuer une stratégie d’archivage aux utilisateurs de Skype entreprise Server.'
ms.openlocfilehash: 5dbd1624813b187e8c0981aa1a84b6096b79e86a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992781"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Appliquer une stratégie d’archivage aux utilisateurs de Skype entreprise Server

**Résumé :** Découvrez comment attribuer une stratégie d’archivage aux utilisateurs de Skype entreprise Server.
  
Si vous avez créé une ou plusieurs stratégies utilisateur pour l’archivage pour les utilisateurs hébergés sur Skype entreprise Server, vous pouvez implémenter la prise en charge de l’archivage pour des utilisateurs spécifiques en appliquant les stratégies appropriées à ces utilisateurs ou groupes d’utilisateurs. Par exemple, si vous créez une stratégie pour la prise en charge de l’archivage des communications internes, vous pouvez l’appliquer à au moins un utilisateur ou groupe d’utilisateurs pour la prise en charge de l’archivage des communications Skype entreprise Server de l’utilisateur.
  
> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, Exchange stratégies de conservation inaltérable Déterminez si l’archivage est activé pour les utilisateurs hébergés sur Exchange et que leurs boîtes aux lettres sont placées en conservation inaltérable. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md) et configuration de l' [intégration avec le stockage Exchange pour Skype entreprise Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Appliquer une stratégie utilisateur via le Panneau de configuration

Pour appliquer une stratégie utilisateur via le Panneau de configuration :
  
1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne. 
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer. 
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **modifier l’utilisateur de Lync Server** sous **stratégie d’archivage**, sélectionnez la stratégie d’utilisateur d’archivage que vous voulez appliquer.
    
    > [!NOTE]
    > Les ** \<paramètres\> automatiques** appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.
  
6. Cliquez sur **Valider**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Appliquer une stratégie d’utilisateur à l’aide de Windows PowerShell

Vous pouvez également appliquer une stratégie utilisateur à l’aide de l’applet de la cmdlet Windows PowerShell **Grant-CsArchivingPolicy** .
  
La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Cette commande affecte la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs dont les comptes sont hébergés sur le pool de serveurs d’inscriptions atl-cs-001.contoso.com. Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation sur l’applet de commande [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

La commande suivante supprime l’assignation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Pour plus d’informations, reportez-vous à la documentation sur l’applet [de passe Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

