---
title: Modifier les stratégies de conférence de Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Résumé : Découvrez comment modifier les stratégies de conférence de Skype pour Business Server.'
ms.openlocfilehash: 36b6cb92ddb1a6628186198906da87c5dec29532
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878041"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="f8108-103">Modifier les stratégies de conférence de Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="f8108-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="f8108-104">**Résumé :** Découvrez comment modifier les stratégies de conférence de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f8108-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="f8108-105">Vous pouvez modifier les stratégies de conférence à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f8108-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f8108-106">Modifier les stratégies de conférence à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="f8108-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f8108-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f8108-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f8108-108">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="f8108-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f8108-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="f8108-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="f8108-110">Dans la liste des stratégies de conférence, cliquez sur la stratégie à modifier, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f8108-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f8108-111">Dans **Modifier la stratégie de conférence**, modifiez les paramètres de stratégie, à l’exception du nom de la stratégie qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="f8108-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="f8108-112">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f8108-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f8108-113">Modifier les stratégies de conférence à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f8108-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f8108-114">Pour modifier les stratégies de conférence, utilisez l’applet de commande **Set-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="f8108-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="f8108-115">L’exemple qui suit modifie une valeur de propriété de la stratégie de conférence SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="f8108-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="f8108-116">La commande définit la valeur de la propriété AllowConferenceRecording sur False :</span><span class="sxs-lookup"><span data-stu-id="f8108-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="f8108-117">Pour plus d’informations, y compris la syntaxe complète et une liste des paramètres, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f8108-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

