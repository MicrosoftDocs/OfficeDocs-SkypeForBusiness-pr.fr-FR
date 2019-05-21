---
title: Modification des stratégies de conférence dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Résumé: Découvrez comment modifier les stratégies de conférence dans Skype entreprise Server.'
ms.openlocfilehash: b2c192948f0119a70f031c1c2bbe5de8e776c2f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280410"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="4a8fb-103">Modification des stratégies de conférence dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4a8fb-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="4a8fb-104">**Résumé:** Découvrez comment modifier les stratégies de conférence dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="4a8fb-105">Vous pouvez modifier les stratégies de conférence en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4a8fb-106">Modification des stratégies de conférence à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4a8fb-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4a8fb-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="4a8fb-108">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4a8fb-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="4a8fb-110">Dans la liste des stratégies de conférence, cliquez sur la stratégie à modifier, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4a8fb-111">Dans **Modifier la stratégie de conférence**, modifiez les paramètres de stratégie, à l’exception du nom de la stratégie qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="4a8fb-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4a8fb-113">Modification des stratégies de conférence à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="4a8fb-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="4a8fb-114">Pour modifier les stratégies de conférence, utilisez l’applet **de passe Set-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="4a8fb-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="4a8fb-115">L’exemple qui suit modifie une valeur de propriété de la stratégie de conférence SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="4a8fb-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="4a8fb-116">La commande définit la valeur de la propriété AllowConferenceRecording sur False :</span><span class="sxs-lookup"><span data-stu-id="4a8fb-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="4a8fb-117">Pour plus d’informations, y compris la syntaxe complète et une liste de paramètres, consultez la rubrique [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4a8fb-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

