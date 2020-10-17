---
title: 'Lync Server 2013 : définition de l’étendue du déploiement E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27d280580f4d9cae1f6240b554be760d1689daa3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504481"
---
# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="56fa0-102">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56fa0-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56fa0-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="56fa0-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="56fa0-104">Avant de configurer Microsoft Lync Server 2013 pour E9-1-1, vous devez planifier votre déploiement E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="56fa0-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="56fa0-105">Voici certaines des questions que vous pouvez vous poser :</span><span class="sxs-lookup"><span data-stu-id="56fa0-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="56fa0-106">**Quelles sont la stratégie et les obligations légales de votre organisation concernant E9-1-1 ?**</span><span class="sxs-lookup"><span data-stu-id="56fa0-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="56fa0-107">Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre.</span><span class="sxs-lookup"><span data-stu-id="56fa0-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="56fa0-108">Vous devez consulter votre équipe juridique pour comprendre les obligations qui peuvent s’appliquer à votre déploiement de Lync Server dans vos régions géographiques pertinentes.</span><span class="sxs-lookup"><span data-stu-id="56fa0-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="56fa0-109">**Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**</span><span class="sxs-lookup"><span data-stu-id="56fa0-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="56fa0-p103">Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="56fa0-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="56fa0-112">**Comment allez-vous déployer E9-1-1 sur des sites de succursales ?**</span><span class="sxs-lookup"><span data-stu-id="56fa0-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="56fa0-113">La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="56fa0-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="56fa0-114">Si vous avez centralisé des jonctions SIP E-9-1-1 et qu’une panne de réseau étendu se produit, les clients qui se connectent risquent de ne pas pouvoir obtenir un emplacement depuis le service d’informations d’emplacement ou de se connecter au fournisseur de services d’urgence.</span><span class="sxs-lookup"><span data-stu-id="56fa0-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="56fa0-115">Lync Server offre plusieurs stratégies de gestion de la résistance des communications vocales dans les succursales, notamment : les réseaux de données résistants, le déploiement d’une jonction SIP à chaque succursale ou l’envoi d’appels d’urgence à la passerelle locale pendant les pannes.</span><span class="sxs-lookup"><span data-stu-id="56fa0-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="56fa0-116">Pour plus d’informations, reportez-vous à la rubrique [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span><span class="sxs-lookup"><span data-stu-id="56fa0-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="56fa0-117">**Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**</span><span class="sxs-lookup"><span data-stu-id="56fa0-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="56fa0-p105">L’acquisition d’emplacement automatique n’est disponible que pour les clients se trouvant sur le réseau de l’organisation, votre société doit donc décider si elle prendra en charge les appels E9-1-1 effectués à partir de clients Lync en dehors du site. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Toutefois, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).</span><span class="sxs-lookup"><span data-stu-id="56fa0-p105">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises. For example, will you enable users to place emergency calls if they are working from home or from a customer site? If a client is located outside the enterprise network, the client can be configured to prompt the user for a location. However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56fa0-122">Les clients Lync des utilisateurs qui se connectent au réseau de votre organisation à l’aide du VPN peuvent récupérer les informations d’adresse IP interne, mais ces adresses ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN soient exclus du service informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="56fa0-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="56fa0-123">**Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**</span><span class="sxs-lookup"><span data-stu-id="56fa0-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="56fa0-p106">Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau PSTN pour acheminer l’appel via une passerelle PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="56fa0-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

