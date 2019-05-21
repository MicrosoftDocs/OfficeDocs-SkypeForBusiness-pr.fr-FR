---
title: Supprimer une stratégie d’archivage existante dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Résumé: Découvrez comment supprimer une stratégie d’archivage pour Skype entreprise Server.'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278411"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="90cbc-103">Supprimer une stratégie d’archivage existante dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="90cbc-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="90cbc-104">**Résumé:** Découvrez comment supprimer une stratégie d’archivage de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="90cbc-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="90cbc-105">Vous pouvez supprimer une stratégie utilisateur ou une stratégie de site mais la stratégie globale ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="90cbc-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="90cbc-106">Si vous supprimez la politique globale, Skype entreprise Server réinitialise automatiquement la stratégie aux valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="90cbc-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="90cbc-107">Supprimer une stratégie via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="90cbc-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="90cbc-108">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="90cbc-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="90cbc-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="90cbc-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="90cbc-110">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.</span><span class="sxs-lookup"><span data-stu-id="90cbc-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="90cbc-111">Dans la liste des stratégies d’archivage, cliquez sur la stratégie utilisateur ou la stratégie de site que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="90cbc-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="90cbc-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="90cbc-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="90cbc-113">Supprimer une stratégie via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90cbc-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="90cbc-114">Vous pouvez également supprimer des stratégies d’archivage via l’applet de commande **Remove-CsArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="90cbc-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="90cbc-p102">Par exemple, la commande suivante supprime la stratégie avec la syntaxe Identity site:Redmond. Lorsqu’une stratégie configurée au niveau du site est supprimée, les utilisateurs précédemment gérés par cette stratégie utilisent automatiquement à la place la stratégie d’archivage globale :</span><span class="sxs-lookup"><span data-stu-id="90cbc-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="90cbc-117">Cette commande permet de supprimer toutes les stratégies d’archivage appliquées au niveau Utilisateur :</span><span class="sxs-lookup"><span data-stu-id="90cbc-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="90cbc-118">Cette commande permet de supprimer toutes les stratégies d’archivage où l’archivage interne a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="90cbc-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="90cbc-119">Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="90cbc-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
