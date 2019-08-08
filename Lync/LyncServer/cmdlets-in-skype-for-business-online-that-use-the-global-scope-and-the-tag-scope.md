---
title: Cmdlets dans Skype entreprise Online utilisant l’étendue globale et l’étendue des indicateurs
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233098"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="a3fb1-102">Cmdlets dans Skype entreprise Online utilisant l’étendue globale et l’étendue des indicateurs</span><span class="sxs-lookup"><span data-stu-id="a3fb1-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="a3fb1-103">Dans Skype entreprise Online, les stratégies peuvent être configurées au niveau de l’étendue *globale* ou au niveau de l' *étendue* des balises (ou d’une *étendue par utilisateur*).</span><span class="sxs-lookup"><span data-stu-id="a3fb1-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="a3fb1-104">Lorsque vous utilisez les applets **de cmdlet Get-CS** , vous n’avez pas à spécifier une étendue ou une identité.</span><span class="sxs-lookup"><span data-stu-id="a3fb1-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="a3fb1-105">Si vous appelez l’une de ces applets de lignes sans paramètre, tous les éléments appropriés seront renvoyés.</span><span class="sxs-lookup"><span data-stu-id="a3fb1-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="a3fb1-106">Par exemple, cette commande renvoie des informations sur toutes les stratégies d’accès externe:</span><span class="sxs-lookup"><span data-stu-id="a3fb1-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="a3fb1-107">Vous devez inclure uniquement le paramètre Identity ou Filter si vous souhaitez limiter les données renvoyées.</span><span class="sxs-lookup"><span data-stu-id="a3fb1-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="a3fb1-108">Par exemple, pour renvoyer uniquement la stratégie globale, utilisez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="a3fb1-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="a3fb1-109">Pour renvoyer une stratégie par utilisateur ayant l’identité «RedmondAccessPolicy», utilisez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="a3fb1-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="a3fb1-110">Lorsque vous faites référence à une stratégie par utilisateur, <STRONG></STRONG> le préfixe de balise est facultatif.</span><span class="sxs-lookup"><span data-stu-id="a3fb1-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="a3fb1-111">Cette syntaxe, qui inclut le préfixe, est également valide:</span><span class="sxs-lookup"><span data-stu-id="a3fb1-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="a3fb1-112">Get-CsExternalAccessPolicy-Identity "tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="a3fb1-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="a3fb1-113">Pour renvoyer toutes les stratégies, à l’exception des stratégies globales (c’est-à-dire toutes les stratégies par utilisateur), utilisez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="a3fb1-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="a3fb1-114">Les applets de commande suivantes fonctionnent à la fois sur l’étendue globale et sur l’étendue par utilisateur (balise):</span><span class="sxs-lookup"><span data-stu-id="a3fb1-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="a3fb1-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a3fb1-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a3fb1-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a3fb1-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a3fb1-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a3fb1-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="a3fb1-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="a3fb1-122">Malgré le nom, les plans de numérotation sont des politiques qui s’exécutent de façon fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="a3fb1-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="a3fb1-123">Le <EM>plan</EM> de numérotation est utilisé à la place (par exemple, la stratégie de numérotation) pour conserver la terminologie utilisée avec les versions précédentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3fb1-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="a3fb1-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3fb1-124">See Also</span></span>


[<span data-ttu-id="a3fb1-125">Identités, étendues et clients dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a3fb1-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="a3fb1-126">[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="a3fb1-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

