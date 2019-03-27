---
title: Affecter des stratégies de conférence dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Résumé : Découvrez comment attribuer des stratégies de conférence de Skype pour Business Server.'
ms.openlocfilehash: 44e29842fd11d600aa5a692e98b5ddbb72149ade
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892631"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="6699e-103">Affecter des stratégies de conférence dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6699e-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="6699e-104">**Résumé :** Découvrez comment attribuer des stratégies de conférence de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="6699e-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="6699e-105">Vous pouvez affecter des stratégies de conférence pour les utilisateurs à l’aide de Skype pour Business Server Management Shell et l’applet de commande **Grant-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="6699e-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6699e-106">Affecter des stratégies de conférence à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="6699e-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6699e-107">Dans l’exemple qui suit, la stratégie SalesConferencingPolicy est affectée à l’utilisateur dont l’identité est « Ken Myer » :</span><span class="sxs-lookup"><span data-stu-id="6699e-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="6699e-p101">Dans l’exemple ci-dessous, la stratégie de conférence FinanceConferencingPolicy est affectée à tous les utilisateurs disposant de comptes dans l’unité d’organisation Finance. Pour affecter la même stratégie à tous les utilisateurs d’une unité d’organisation donnée, l’applet de commande Get-CsUser est utilisée pour extraire tous les comptes de cette unité. Une fois tous les comptes extraits, ces informations sont ensuite redirigées vers l’applet de commande Grant-CsConferencingPolicy, qui affecte la stratégie FinanceConferencingPolicy à chaque utilisateur de la collection.</span><span class="sxs-lookup"><span data-stu-id="6699e-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="6699e-111">Pour plus d’informations, y compris la syntaxe complète et une liste des paramètres, voir [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6699e-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

