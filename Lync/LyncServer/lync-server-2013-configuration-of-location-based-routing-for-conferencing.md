---
title: 'Lync Server 2013 : configuration du routage géodépendant pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bc901b9ef1b4b358771427f44d220631e4a40ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="3d57d-102">Configuration du routage géodépendant pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d57d-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d57d-103">_**Dernière modification de la rubrique :** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="3d57d-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="3d57d-104">L’application de conférence de routage basée sur l’emplacement repose sur la configuration de l’acheminement géodépendant de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d57d-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="3d57d-105">Les configurations principales sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d57d-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="3d57d-106">L’emplacement des participants qui rejoignent une réunion est déterminé en fonction de leur site réseau.</span><span class="sxs-lookup"><span data-stu-id="3d57d-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="3d57d-107">Un site réseau et ses sous-réseaux associés doivent être définis dans Lync Server afin d’appliquer le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="3d57d-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="3d57d-108">Pour appliquer le routage géodépendant des réunions, les participants Lync doivent être activés pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="3d57d-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="3d57d-109">Pour appliquer le routage géodépendant des points de terminaison PSTN joignant des réunions, la jonction SIP utilisée pour connecter les points de terminaison PSTN doit être configurée pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="3d57d-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="3d57d-110">Pour plus d’informations sur le déploiement et la configuration du routage géodépendant de Lync Server 2013, reportez-vous à la rubrique Configuring [location-based Routing](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3d57d-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="3d57d-111">Activation de l’application de conférence de routage basée sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="3d57d-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="3d57d-112">L’application de conférence de routage basée sur l’emplacement est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="3d57d-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="3d57d-113">Avant d’activer cette application, vous devez déterminer la priorité appropriée à affecter à l’application.</span><span class="sxs-lookup"><span data-stu-id="3d57d-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="3d57d-114">Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="3d57d-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="3d57d-115">Get-CsServerApplication-Identity service : Registrar\<: nom de domaine complet du pool\></span><span class="sxs-lookup"><span data-stu-id="3d57d-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="3d57d-116">Dans cette applet de \<commande,\> le nom de domaine complet du pool est le pool dans lequel l’application de conférence de routage basée sur l’emplacement doit être activée.</span><span class="sxs-lookup"><span data-stu-id="3d57d-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="3d57d-117">Cette applet de commande renvoie la liste des applications hébergées par Lync Server et la valeur de priorité pour chacune d’entre elles.</span><span class="sxs-lookup"><span data-stu-id="3d57d-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="3d57d-118">L’application de conférence de routage basée sur l’emplacement doit disposer d’une valeur de priorité supérieure à celle de l’application « UdcAgent » et plus petite que les applications « DefaultRouting », « ExumRouting » et « OutboundRouting ».</span><span class="sxs-lookup"><span data-stu-id="3d57d-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="3d57d-119">Nous vous recommandons d’affecter à l’application de conférence de routage basée sur l’emplacement une valeur de priorité supérieure d’un point à la valeur de priorité de l’application « UdcAgent ».</span><span class="sxs-lookup"><span data-stu-id="3d57d-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="3d57d-120">Par exemple, si l’application « UdcAgent » a une valeur de priorité « 2 », l’application « DefaultRouting » a une valeur de priorité « 8 », l’application « ExumRouting » a une valeur de priorité de « 9 » et l’application « OutboundRouting » a une valeur de priorité de « 10 », puis vous devez attribuer à l’application de conférence de routage basée sur l’emplacement une valeur de priorité de « 3 ».</span><span class="sxs-lookup"><span data-stu-id="3d57d-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="3d57d-121">Cette opération placerait la priorité des applications dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence de routage basée sur l’emplacement (Priority : 3), autres applications (priorités : 4 à 8), " DefaultRouting "(Priority : 9)," ExumRouting "(Priority : 10) et" OutboundRouting "(Priority : 11).</span><span class="sxs-lookup"><span data-stu-id="3d57d-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="3d57d-122">Une fois que vous avez trouvé la valeur de priorité correcte pour l’application de conférence de routage basée sur l’emplacement, tapez l’applet de commande suivante pour chaque pool frontal ou serveur Standard Edition dont les utilisateurs sont activés pour le routage géodépendant :</span><span class="sxs-lookup"><span data-stu-id="3d57d-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="3d57d-123">New-CsServerApplication-Identity service : Registrar\<: pool\>de nom de \<domaine complet\> /LBRouting-Priority Application Priority enabled $true-URI Critical $true-URIhttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="3d57d-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="3d57d-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3d57d-124">For example:</span></span>

<span data-ttu-id="3d57d-125">New-CsServerApplication-Identity service :Registrar :LS2013CU2LBRPool. contoso. com/LBRouting-Optional 3-enabled $true-URI $true-URIhttps://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="3d57d-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri https://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="3d57d-126">Après avoir utilisé cette applet de commande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition où l’application de conférence de routage basée sur l’emplacement a été activée.</span><span class="sxs-lookup"><span data-stu-id="3d57d-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3d57d-127">Les conditions de routage géodépendant des conférences ou des transferts consultatifs ne sont pas appliquées tant que tous les serveurs frontaux dans les pools applicables ou les serveurs Standard Edition Server ne sont pas redémarrés.</span><span class="sxs-lookup"><span data-stu-id="3d57d-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="3d57d-128">Une fois que l’application de conférence de routage basée sur l’emplacement a été activée et que tous les serveurs Lync concernés ont été redémarrés, toutes les conférences organisées par des utilisateurs Lync activés pour le routage géodépendant sont surveillées pour empêcher le contournement de numéro de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="3d57d-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

