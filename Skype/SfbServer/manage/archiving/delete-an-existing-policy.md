---
title: Supprimer une stratégie d’archivage existante dans Skype Entreprise Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Résumé : Découvrez comment supprimer une stratégie d’archivage pour Skype Entreprise Server.'
ms.openlocfilehash: 2baad7d862b1b6739019a4459492bfb3b67e04cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095388"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="3ff3f-103">Supprimer une stratégie d’archivage existante dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3ff3f-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="3ff3f-104">**Résumé :** Découvrez comment supprimer une stratégie d’archivage pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="3ff3f-105">Vous pouvez supprimer une stratégie utilisateur ou une stratégie de site, mais pas la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="3ff3f-106">Si vous supprimez la stratégie globale, Skype Entreprise Server réinitialise automatiquement la stratégie aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="3ff3f-107">Supprimer une stratégie à l’aide du Panneau de contrôle</span><span class="sxs-lookup"><span data-stu-id="3ff3f-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="3ff3f-108">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3ff3f-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3ff3f-110">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="3ff3f-111">Dans la liste des stratégies d’archivage, cliquez sur la stratégie d’utilisateur ou de site à supprimer, cliquez sur **Modifier,** puis sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="3ff3f-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="3ff3f-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="3ff3f-113">Supprimer une stratégie à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ff3f-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="3ff3f-114">Vous pouvez également supprimer des stratégies d’archivage à l’aide de l’cmdlet **Remove-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3ff3f-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="3ff3f-115">Par exemple, la commande suivante supprime la stratégie dont l’identité est site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="3ff3f-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="3ff3f-116">Lorsqu’une stratégie configurée au niveau du site est supprimée, les utilisateurs précédemment gérés par la stratégie de site sont automatiquement régis par la stratégie d’archivage globale à la place :</span><span class="sxs-lookup"><span data-stu-id="3ff3f-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="3ff3f-117">Cette commande supprime toutes les stratégies d’archivage appliquées au niveau utilisateur :</span><span class="sxs-lookup"><span data-stu-id="3ff3f-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="3ff3f-118">Cette commande supprime toutes les stratégies d’archivage pour laquelle l’archivage interne a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="3ff3f-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="3ff3f-119">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Remove-CsArchivingPolicy.](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3ff3f-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>