---
title: Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838092"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="4dcb0-102">Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité</span><span class="sxs-lookup"><span data-stu-id="4dcb0-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="4dcb0-103">Les applets de passe utilisés lors de la modification des listes autorisées et des listes bloquées (listes qui déterminent les organisations externes avec lesquelles les utilisateurs sont autorisés à communiquer) n’utilisent pas d’étendue ou d’identité.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="4dcb0-104">En fait, l’applet **de nouvelle applet de CsEdgeAllowAllKnownDomains** n’a aucun paramètre.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="4dcb0-105">Les applets de applet qui n’utilisent pas d’étendue ou d’identité sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="4dcb0-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="4dcb0-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4dcb0-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4dcb0-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4dcb0-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4dcb0-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4dcb0-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="4dcb0-109">Notez que, avec l’applet **de nouvelle cmdlet New-CsEdgeAllowList** et la cmdlet **New-CsEdgeDomainPattern** , vous devez inclure le paramètre domain.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="4dcb0-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4dcb0-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="4dcb0-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4dcb0-111">See Also</span></span>


[<span data-ttu-id="4dcb0-112">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4dcb0-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="4dcb0-113">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4dcb0-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

