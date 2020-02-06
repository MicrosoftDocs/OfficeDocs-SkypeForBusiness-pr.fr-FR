---
title: Attribution de stratégies de conférence dans Skype entreprise Server
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
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Résumé : Découvrez comment attribuer des stratégies de conférence dans Skype entreprise Server.'
ms.openlocfilehash: c5dfb9c2aa186bf199a066c82e3687aade564905
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818656"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="4a4c5-103">Attribution de stratégies de conférence dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4a4c5-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="4a4c5-104">**Résumé :** Découvrez comment attribuer des stratégies de conférence dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4a4c5-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="4a4c5-105">Vous pouvez attribuer des stratégies de conférence aux utilisateurs à l’aide de Skype entreprise Server Management Shell et de l’applet de passe **Grant-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="4a4c5-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4a4c5-106">Attribution de stratégies de conférence à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="4a4c5-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="4a4c5-107">Dans l’exemple qui suit, la stratégie SalesConferencingPolicy est affectée à l’utilisateur dont l’identité est « Ken Myer » :</span><span class="sxs-lookup"><span data-stu-id="4a4c5-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="4a4c5-p101">Dans l’exemple ci-dessous, la stratégie de conférence FinanceConferencingPolicy est affectée à tous les utilisateurs disposant de comptes dans l’unité d’organisation Finance. Pour affecter la même stratégie à tous les utilisateurs d’une unité d’organisation donnée, l’applet de commande Get-CsUser est utilisée pour extraire tous les comptes de cette unité. Une fois tous les comptes extraits, ces informations sont ensuite redirigées vers l’applet de commande Grant-CsConferencingPolicy, qui affecte la stratégie FinanceConferencingPolicy à chaque utilisateur de la collection.</span><span class="sxs-lookup"><span data-stu-id="4a4c5-p101">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit. To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU. After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="4a4c5-111">Pour plus d’informations, y compris la syntaxe complète et une liste de paramètres, consultez la rubrique [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4a4c5-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

