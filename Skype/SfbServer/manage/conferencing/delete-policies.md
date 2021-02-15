---
title: Supprimer des stratégies de conférence dans Skype Entreprise Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Résumé : Découvrez comment supprimer des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: eedb0b3676f0cc046e6096dca2cb1ec5ced5d6ec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828194"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="53ab9-103">Supprimer des stratégies de conférence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="53ab9-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="53ab9-104">**Résumé :** Découvrez comment supprimer des stratégies de conférence dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53ab9-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="53ab9-105">Vous pouvez supprimer des stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="53ab9-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="53ab9-106">Supprimer des stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="53ab9-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="53ab9-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="53ab9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="53ab9-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="53ab9-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="53ab9-109">Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur Stratégie **de conférence.**</span><span class="sxs-lookup"><span data-stu-id="53ab9-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="53ab9-110">Dans la liste des stratégies de conférence, cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **Modifier,** puis sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="53ab9-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="53ab9-111">Supprimer des stratégies de conférence à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="53ab9-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="53ab9-112">Pour supprimer des stratégies de conférence, utilisez l’cmdlet **Remove-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="53ab9-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="53ab9-113">La commande suivante permet de supprimer la stratégie de conférence dont le paramètre Identity a la valeur RedmondConferencingPolicy :</span><span class="sxs-lookup"><span data-stu-id="53ab9-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="53ab9-114">La commande suivante supprime toutes les stratégies de conférence qui permettent aux utilisateurs externes d’enregistrer la conférence :</span><span class="sxs-lookup"><span data-stu-id="53ab9-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="53ab9-115">Pour plus d’informations, notamment sur la syntaxe complète et la liste des paramètres, voir [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="53ab9-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

