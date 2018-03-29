---
title: Suppression d’une stratégie d’archivage existante dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Résumé : Découvrez comment supprimer une stratégie d’archivage pour Skype pour Business Server 2015.'
ms.openlocfilehash: aeb640cc832bffbded4765e5b6cc931a17365215
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="e434c-103">Suppression d’une stratégie d’archivage existante dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="e434c-103">Delete an existing archiving policy in Skype for Business Server 2015</span></span>

<span data-ttu-id="e434c-104">**Résumé :** Découvrez comment supprimer une stratégie d’archivage pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e434c-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e434c-105">Vous pouvez supprimer une stratégie utilisateur ou une stratégie de site mais la stratégie globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="e434c-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="e434c-106">Si vous supprimez la stratégie globale, Skype pour Business Server réinitialise automatiquement la stratégie pour les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="e434c-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="e434c-107">Supprimer une stratégie via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="e434c-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="e434c-108">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e434c-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e434c-109">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="e434c-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e434c-110">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="e434c-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="e434c-111">Dans la liste des stratégies d’archivage, cliquez sur la stratégie utilisateur ou la stratégie de site que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e434c-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="e434c-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e434c-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="e434c-113">Supprimer une stratégie via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e434c-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="e434c-114">Vous pouvez également supprimer des stratégies d’archivage via l’applet de commande **Remove-CsArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="e434c-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e434c-p102">Par exemple, la commande suivante supprime la stratégie avec la syntaxe Identity site:Redmond. Lorsqu’une stratégie configurée au niveau du site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :</span><span class="sxs-lookup"><span data-stu-id="e434c-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="e434c-117">Cette commande permet de supprimer toutes les stratégies d’archivage appliquées au niveau Utilisateur :</span><span class="sxs-lookup"><span data-stu-id="e434c-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="e434c-118">Cette commande permet de supprimer toutes les stratégies d’archivage où l’archivage interne a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="e434c-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="e434c-119">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e434c-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>