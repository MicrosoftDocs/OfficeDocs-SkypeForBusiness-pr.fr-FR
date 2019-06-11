---
title: 'Lync Server 2013: attribuer des stratégies à un téléphone de zone commune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="8c13c-102">Attribuer des stratégies dans Lync Server 2013 à un téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="8c13c-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c13c-103">_**Dernière modification de la rubrique:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8c13c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8c13c-104">Après avoir créé votre stratégie pour les téléphones communs (pour plus de détails, consultez la rubrique [créer une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), vous pouvez attribuer la stratégie à un téléphone local en utilisant Windows PowerShell et l' \*\*autorisation d’attribution-CS appropriée. \*\*cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8c13c-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="8c13c-105">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c13c-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8c13c-106">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="8c13c-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="8c13c-107">Attribution d’une stratégie à un seul téléphone standard</span><span class="sxs-lookup"><span data-stu-id="8c13c-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="8c13c-108">La commande suivante affecte le RedmondVoice de la stratégie vocale par utilisateur au téléphone local qui dispose de l’identité bâtiment 14 lobby.</span><span class="sxs-lookup"><span data-stu-id="8c13c-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="8c13c-109">Attribution d’une stratégie à plusieurs téléphones de surface commune</span><span class="sxs-lookup"><span data-stu-id="8c13c-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="8c13c-110">Dans cet exemple, la stratégie vocale RedmondVoice est affectée à l’ensemble des téléphones communs configurés pour une utilisation au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8c13c-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="8c13c-111">Pour plus d’informations, reportez-vous aux rubriques d’aide pour le [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="8c13c-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c13c-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c13c-112">See Also</span></span>


[<span data-ttu-id="8c13c-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="8c13c-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

