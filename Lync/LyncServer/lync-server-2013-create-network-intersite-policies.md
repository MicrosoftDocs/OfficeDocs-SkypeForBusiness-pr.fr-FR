---
title: 'Lync Server 2013 : création de stratégies intersite réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae7024aa0a9f5c5734762ed0accb6e1dc723f2b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="7d5d4-102">Créer des stratégies inter-sites réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d5d4-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d5d4-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7d5d4-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7d5d4-104">Une *stratégie intersite réseau* définit des limitations de bande passante entre des sites présentant des liens directs WAN entre eux.</span><span class="sxs-lookup"><span data-stu-id="7d5d4-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="7d5d4-105">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d5d4-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="7d5d4-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d5d4-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="7d5d4-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d5d4-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="7d5d4-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d5d4-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="7d5d4-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d5d4-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7d5d4-110">Une stratégie intersite réseau est nécessaire <EM>uniquement</EM> s’il existe un lien d’accès direct entre deux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="7d5d4-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="7d5d4-111">Dans la région Amérique du Nord de l’exemple de topologie, il existe un lien direct entre les sites Reno et Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="7d5d4-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="7d5d4-112">Ces deux sites nécessitent une stratégie intersite qui applique un profil de stratégie de bande passante approprié.</span><span class="sxs-lookup"><span data-stu-id="7d5d4-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="7d5d4-113">L’exemple suivant applique le profil\_de lien 20Mo.</span><span class="sxs-lookup"><span data-stu-id="7d5d4-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="7d5d4-114">Pour créer une stratégie intersite réseau</span><span class="sxs-lookup"><span data-stu-id="7d5d4-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="7d5d4-115">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7d5d4-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7d5d4-p102">Exécutez l’applet de commande New-CsNetworkInterSitePolicy pour créer des stratégies intersite réseau et appliquez un profil de stratégie de bande passante approprié pour deux sites qui présentent un lien d’accès direct. Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="7d5d4-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="7d5d4-118">Répétez l’étape 2 autant que nécessaire, afin de créer des stratégies intersite réseau pour toutes les paires de sites réseau qui présentent un lien d’accès direct.</span><span class="sxs-lookup"><span data-stu-id="7d5d4-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

