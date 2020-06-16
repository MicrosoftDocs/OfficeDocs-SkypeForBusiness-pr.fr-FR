---
title: Applets de commande dans Skype entreprise Online qui utilisent l’étendue globale et l’étendue de la balise
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755074"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="7ace3-102">Applets de commande dans Skype entreprise Online qui utilisent l’étendue globale et l’étendue de la balise</span><span class="sxs-lookup"><span data-stu-id="7ace3-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="7ace3-103">Dans Skype entreprise Online, les stratégies peuvent être configurées au niveau de l’étendue *globale* ou de l’étendue de la *balise* (ou *étendue par utilisateur*).</span><span class="sxs-lookup"><span data-stu-id="7ace3-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="7ace3-104">Lorsque vous utilisez les cmdlets **Get-CS** , il n’est pas nécessaire de spécifier une étendue ou une identité.</span><span class="sxs-lookup"><span data-stu-id="7ace3-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="7ace3-105">Si vous appelez l’une de ces applets de commande sans aucun paramètre, tous les éléments pertinents seront retournés.</span><span class="sxs-lookup"><span data-stu-id="7ace3-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="7ace3-106">Par exemple, cette commande renvoie des informations sur toutes les stratégies d’accès externe :</span><span class="sxs-lookup"><span data-stu-id="7ace3-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="7ace3-107">Si vous souhaitez limiter les données renvoyées, vous devez inclure uniquement le paramètre Identity ou le paramètre Filter.</span><span class="sxs-lookup"><span data-stu-id="7ace3-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="7ace3-108">Par exemple, pour renvoyer uniquement la stratégie globale, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7ace3-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="7ace3-109">Pour renvoyer une stratégie par utilisateur dont l’identité est « RedmondAccessPolicy », utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7ace3-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="7ace3-110">Lorsque vous faites référence à une stratégie utilisateur, le <STRONG>préfixe</STRONG> de balise est facultatif.</span><span class="sxs-lookup"><span data-stu-id="7ace3-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="7ace3-111">Cette syntaxe, qui inclut le préfixe, est également valide :</span><span class="sxs-lookup"><span data-stu-id="7ace3-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="7ace3-112">Get-CsExternalAccessPolicy – Identity "tag : RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="7ace3-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="7ace3-113">Pour renvoyer toutes les stratégies à l’exception des stratégies globales (c’est-à-dire, toutes les stratégies par utilisateur), utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7ace3-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="7ace3-114">Les applets de commande suivantes fonctionnent sur l’étendue globale et sur l’étendue par utilisateur (balise) :</span><span class="sxs-lookup"><span data-stu-id="7ace3-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="7ace3-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7ace3-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7ace3-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7ace3-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7ace3-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7ace3-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7ace3-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="7ace3-122">Malgré le nom, les plans de numérotation sont des stratégies, de façon fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="7ace3-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="7ace3-123">Le terme <EM>plan de numérotation</EM> est utilisé à la place, par exemple, de la stratégie de numérotation, afin de préserver la terminologie utilisée avec les versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ace3-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="7ace3-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ace3-124">See Also</span></span>


[<span data-ttu-id="7ace3-125">Identités, étendues et locataires dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7ace3-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="7ace3-126">[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7ace3-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

