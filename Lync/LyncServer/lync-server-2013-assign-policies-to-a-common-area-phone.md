---
title: 'Lync Server 2013 : affecter des stratégies à un téléphone de partie commune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dfe908f2bb4ca66714d3eef756a0c53c7334fd7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="8148c-102">Affecter des stratégies dans Lync Server 2013 à un téléphone de partie commune</span><span class="sxs-lookup"><span data-stu-id="8148c-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8148c-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8148c-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8148c-104">Une fois que vous avez créé votre stratégie pour les téléphones de partie commune (pour plus de détails, voir [Create a Voice Policy and configure PSTN usage Records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), vous pouvez affecter la stratégie à un téléphone de partie commune à l’aide de Windows PowerShell et de la cmdlet **Grant-CS** appropriée.</span><span class="sxs-lookup"><span data-stu-id="8148c-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="8148c-105">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8148c-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8148c-106">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="8148c-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="8148c-107">Affectation d’une stratégie à un seul téléphone de partie commune</span><span class="sxs-lookup"><span data-stu-id="8148c-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="8148c-108">La commande suivante affecte la stratégie de voix par utilisateur RedmondVoice au téléphone de partie commune qui possède l’identité Building 14 lobby.</span><span class="sxs-lookup"><span data-stu-id="8148c-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="8148c-109">Affectation d’une stratégie à plusieurs téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="8148c-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="8148c-110">Dans cet exemple, la stratégie de voix par utilisateur RedmondVoice est affectée à tous les téléphones de partie commune configurés pour être utilisés dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="8148c-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="8148c-111">Pour plus d’informations, consultez les rubriques d’aide relatives à [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="8148c-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8148c-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8148c-112">See Also</span></span>


[<span data-ttu-id="8148c-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="8148c-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

