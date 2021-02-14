---
title: Attribuer des stratégies de conférence dans Skype Entreprise Server
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
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Résumé : Découvrez comment affecter des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: d13710d2cc4f6edf1cee16cbc9aa77799ceec8a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806474"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="8b816-103">Attribuer des stratégies de conférence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8b816-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="8b816-104">**Résumé :** Découvrez comment affecter des stratégies de conférence dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8b816-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="8b816-105">Vous pouvez affecter des stratégies de conférence à des utilisateurs à l’aide de Skype Entreprise Server Management Shell et de **l';grant-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="8b816-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8b816-106">Affecter des stratégies de conférence à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8b816-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8b816-107">Dans l’exemple suivant, la stratégie SalesConferencingPolicy est affectée à l’utilisateur dont l’identité est « Ken Myer » :</span><span class="sxs-lookup"><span data-stu-id="8b816-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="8b816-108">Dans l’exemple suivant, la stratégie de conférence FinanceConferencingPolicy est affectée à tous les utilisateurs qui ont des comptes dans l’unité d’organisation Finance.</span><span class="sxs-lookup"><span data-stu-id="8b816-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="8b816-109">Pour affecter la même stratégie à tous les utilisateurs d’une unité d’organisation donnée, l’applet de commande Get-CsUser est utilisée pour récupérer tous les comptes de cette unité.</span><span class="sxs-lookup"><span data-stu-id="8b816-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="8b816-110">Une fois les comptes d’utilisateur récupérés, ces informations sont ensuite canales vers l’cmdlet Grant-CsConferencingPolicy qui affecte la stratégie FinanceConferencingPolicy à chaque utilisateur de la collection :</span><span class="sxs-lookup"><span data-stu-id="8b816-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="8b816-111">Pour plus d’informations, notamment sur la syntaxe complète et la liste des paramètres, voir [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8b816-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
  

