---
title: Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad366315bbc4acf5afb417262da92a5683a084df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001729"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="f3151-102">Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité</span><span class="sxs-lookup"><span data-stu-id="f3151-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="f3151-103">Les applets de commande utilisées lors de la modification des listes autorisées et des listes bloquées (listes qui déterminent les organisations externes avec lesquelles vos utilisateurs sont autorisés à communiquer) n’utilisent ni une étendue ni une identité.</span><span class="sxs-lookup"><span data-stu-id="f3151-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="f3151-104">En fait, la cmdlet **New-CsEdgeAllowAllKnownDomains** n’a aucun paramètre.</span><span class="sxs-lookup"><span data-stu-id="f3151-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="f3151-105">Les applets de commande qui n’utilisent ni une étendue ni une identité sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f3151-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="f3151-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f3151-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f3151-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f3151-107">[New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="f3151-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f3151-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="f3151-109">Notez que, avec la cmdlet **New-CsEdgeAllowList** et la cmdlet **New-CsEdgeDomainPattern** , vous devez inclure le paramètre domain.</span><span class="sxs-lookup"><span data-stu-id="f3151-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="f3151-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f3151-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="f3151-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3151-111">See Also</span></span>


[<span data-ttu-id="f3151-112">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="f3151-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="f3151-113">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f3151-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

