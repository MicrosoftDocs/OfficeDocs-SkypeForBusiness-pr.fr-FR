---
title: 'Lync Server 2013 : hybride et Split-Domain-autodiscover'
description: 'Lync Server 2013 : hybride et Split-Domain-autodiscover.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972233fd10d2b68a002d2d3a203f61bb0bd29574
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554880"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a><span data-ttu-id="9e86c-103">Découverte automatique de domaine hybride et fractionné dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e86c-103">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e86c-104">_**Dernière modification de la rubrique :** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="9e86c-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="9e86c-105">Un espace d’adressage SIP partagé, également appelé déploiement de *domaine scindé* , ou déploiement *hybride* , est une configuration où les utilisateurs sont déployés dans un déploiement local et un environnement en ligne.</span><span class="sxs-lookup"><span data-stu-id="9e86c-105">A shared SIP address space, also known as a *split-domain* deployment, or a *hybrid* deployment, is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="9e86c-106">Le résultat souhaité est qu’un utilisateur, quel que soit l’emplacement de son serveur d’accueil (local ou en ligne), se connecte au déploiement et soit redirigé vers son serveur d’origine.</span><span class="sxs-lookup"><span data-stu-id="9e86c-106">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="9e86c-107">Pour ce faire, la fonctionnalité de découverte automatique de Lync Server 2013 est utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne.</span><span class="sxs-lookup"><span data-stu-id="9e86c-107">To accomplish this, the Autodiscover feature of Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="9e86c-108">Pour ce faire, vous pouvez configurer l’URL (Uniform Resource Locator) de découverte automatique à l’aide de Lync Server Management Shell, de la cmdlet **Get-CsHostingProvider** et de la cmdlet **Set-CsHostingProvider** .</span><span class="sxs-lookup"><span data-stu-id="9e86c-108">You can do this by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell, the **Get-CsHostingProvider** cmdlet, and the **Set-CsHostingProvider** cmdlet.</span></span>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="9e86c-109">Mobilité pour le déploiement dans un domaine séparé</span><span class="sxs-lookup"><span data-stu-id="9e86c-109">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="9e86c-110">Vous devrez recueillir et enregistrer les attributs déployés suivants :</span><span class="sxs-lookup"><span data-stu-id="9e86c-110">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="9e86c-111">À partir de Lync Server Management Shell, tapez</span><span class="sxs-lookup"><span data-stu-id="9e86c-111">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="9e86c-112">Dans les résultats, recherchez le fournisseur en ligne avec l’attribut **ProxyFQDN**.</span><span class="sxs-lookup"><span data-stu-id="9e86c-112">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="9e86c-113">Par exemple, sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e86c-113">For example, sipfed.online.lync.com.</span></span>

  - <span data-ttu-id="9e86c-114">Enregistrez la valeur de ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="9e86c-114">Record the value of the ProxyFQDN.</span></span>

  - <span data-ttu-id="9e86c-115">Activez la Fédération dans le panneau de configuration Lync Server sur site, en autorisant la Fédération avec le fournisseur en ligne.</span><span class="sxs-lookup"><span data-stu-id="9e86c-115">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider.</span></span>

  - <span data-ttu-id="9e86c-116">Activez la fédération pour le fournisseur en ligne.</span><span class="sxs-lookup"><span data-stu-id="9e86c-116">Enable federation for the online provider.</span></span> <span data-ttu-id="9e86c-117">Par défaut, tous les utilisateurs en ligne sont activés pour la Fédération de domaine et peuvent communiquer avec tous les domaines.</span><span class="sxs-lookup"><span data-stu-id="9e86c-117">By default, all online users are enabled for domain federation and can communicate with all domains.</span></span>

  - <span data-ttu-id="9e86c-118">Si vous définissez des domaines bloqués et autorisés, déterminez les domaines que vous autorisez explicitement ou bloquez explicitement.</span><span class="sxs-lookup"><span data-stu-id="9e86c-118">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block.</span></span>

  - <span data-ttu-id="9e86c-119">Pour la Fédération en ligne, vous devez planifier les exceptions de pare-feu, les certificats et l’hôte DNS (A ou AAAA, si vous utilisez le protocole IPv6).</span><span class="sxs-lookup"><span data-stu-id="9e86c-119">For online federation, you must plan for firewall exceptions, certificates, and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="9e86c-120">En outre, vous devez configurer les stratégies de fédération.</span><span class="sxs-lookup"><span data-stu-id="9e86c-120">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="9e86c-121">Pour plus d’informations, reportez-vous à la rubrique [Planning for Lync Server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span><span class="sxs-lookup"><span data-stu-id="9e86c-121">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

