---
title: 'Lync Server 2013 : attribuer des stratégies à un téléphone de zone commune'
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
ms.openlocfilehash: e19e2fccabe4759f8cf4cf5eb55ade7e68e2b560
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="3b62e-102">Attribuer des stratégies dans Lync Server 2013 à un téléphone de zone commune</span><span class="sxs-lookup"><span data-stu-id="3b62e-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b62e-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3b62e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3b62e-104">Après avoir créé votre stratégie de téléphone pour les zones communes (pour plus de détails, voir [créer une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), vous pouvez affecter la stratégie à un téléphone réseau commun en utilisant Windows PowerShell et l’applet **de commande Grant-CS** appropriée.</span><span class="sxs-lookup"><span data-stu-id="3b62e-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="3b62e-105">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b62e-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3b62e-106">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="3b62e-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="3b62e-107">Attribution d’une stratégie à un seul téléphone standard</span><span class="sxs-lookup"><span data-stu-id="3b62e-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="3b62e-108">La commande suivante affecte le RedmondVoice de la stratégie vocale par utilisateur au téléphone local qui dispose de l’identité bâtiment 14 lobby.</span><span class="sxs-lookup"><span data-stu-id="3b62e-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="3b62e-109">Attribution d’une stratégie à plusieurs téléphones de surface commune</span><span class="sxs-lookup"><span data-stu-id="3b62e-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="3b62e-110">Dans cet exemple, la stratégie vocale RedmondVoice est affectée à l’ensemble des téléphones communs configurés pour une utilisation au sein de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="3b62e-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="3b62e-111">Pour plus d’informations, reportez-vous aux rubriques d’aide pour le [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="3b62e-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b62e-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3b62e-112">See Also</span></span>


[<span data-ttu-id="3b62e-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="3b62e-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

