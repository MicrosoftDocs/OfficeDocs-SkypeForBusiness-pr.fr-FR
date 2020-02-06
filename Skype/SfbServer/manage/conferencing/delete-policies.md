---
title: Supprimer des stratégies de conférence dans Skype entreprise Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Résumé : Découvrez comment supprimer des stratégies de conférence dans Skype entreprise Server.'
ms.openlocfilehash: 3fe5b8c2bb12f48cb6e904df2fe43c6c8a01e3f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818595"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="e2cee-103">Supprimer des stratégies de conférence dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e2cee-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="e2cee-104">**Résumé :** Découvrez comment supprimer des stratégies de conférence dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e2cee-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="e2cee-105">Vous pouvez supprimer des stratégies de conférence en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2cee-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e2cee-106">Supprimer des stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e2cee-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e2cee-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e2cee-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e2cee-108">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e2cee-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e2cee-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="e2cee-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="e2cee-110">Dans la liste des stratégies de conférence, cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e2cee-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e2cee-111">Supprimer des stratégies de conférence à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e2cee-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e2cee-112">Pour supprimer des stratégies de conférence, utilisez l’applet de commande **Remove-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="e2cee-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="e2cee-113">La commande suivante permet de supprimer la stratégie de conférence dont le paramètre Identity a la valeur RedmondConferencingPolicy :</span><span class="sxs-lookup"><span data-stu-id="e2cee-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="e2cee-114">La commande ci-dessous permet de supprimer toutes les stratégies de conférence qui autorisent les utilisateurs externes à enregistrer la conférence :</span><span class="sxs-lookup"><span data-stu-id="e2cee-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="e2cee-115">Pour plus d’informations, y compris la syntaxe complète et une liste de paramètres, consultez la rubrique [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e2cee-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

