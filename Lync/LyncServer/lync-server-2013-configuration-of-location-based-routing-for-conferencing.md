---
title: 'Lync Server 2013 : configuration du routage géodépendant pour les conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657978ee622713ffd830d4aeb92a05d949287568
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="4683b-102">Configuration du routage géodépendant pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4683b-102">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4683b-103">_**Dernière modification de la rubrique:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="4683b-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="4683b-104">L’application de conférence de routage basée sur l’emplacement repose sur la configuration du routage de l’emplacement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4683b-104">The Location-Based Routing Conferencing application relies on the configuration of Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="4683b-105">Les configurations principales suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="4683b-105">The main configurations are the following:</span></span>

  - <span data-ttu-id="4683b-106">L’emplacement des participants rejoignant une réunion est déterminé sur la base de leur site réseau.</span><span class="sxs-lookup"><span data-stu-id="4683b-106">The location of participants joining a meeting is determined based on their network site.</span></span> <span data-ttu-id="4683b-107">Un site réseau et ses sous-réseaux de réseaux associés doivent être définis dans Lync Server pour appliquer le routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="4683b-107">A network site and its associated network subnets must be defined in Lync Server in order to enforce Location-Based Routing.</span></span>

  - <span data-ttu-id="4683b-108">Pour appliquer le routage de réunions par emplacement, les participants à Lync doivent être activés pour le routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="4683b-108">To enforce Location-Based Routing of meetings, Lync participants must be enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="4683b-109">Pour appliquer le routage de points de terminaison PSTN qui se connecte à l’emplacement de la réunion, le Trunk SIP utilisé pour connecter les points de terminaison PSTN doit être configuré pour le routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="4683b-109">To enforce Location-Based Routing of PSTN endpoints joining meetings, the SIP trunk used to connect the PSTN endpoints must be configured for Location-Based Routing.</span></span>

<span data-ttu-id="4683b-110">Pour plus d’informations sur le déploiement et la configuration du routage en fonction de l’emplacement de Lync Server 2013, consultez la rubrique Configuration du [routage en fonction](lync-server-2013-configuring-location-based-routing.md)de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="4683b-110">For additional information on deploying and configuring Lync Server 2013 Location-Based Routing, please refer Configuring [Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a><span data-ttu-id="4683b-111">Activation de l’application de conférence de routage basée sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="4683b-111">Enabling the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="4683b-112">L’application de conférence de routage basée sur l’emplacement est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4683b-112">The Location-Based Routing Conferencing application is disabled by default.</span></span> <span data-ttu-id="4683b-113">Avant d’activer cette application, vous devez déterminer la priorité adaptée à affecter à l’application.</span><span class="sxs-lookup"><span data-stu-id="4683b-113">Before enabling this application, you need to determine the right priority to assign for the application.</span></span> <span data-ttu-id="4683b-114">Pour déterminer cette priorité, exécutez l’applet de commande suivante dans Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="4683b-114">To determine this priority, run the following cmdlet in Lync Server Management Shell:</span></span>

<span data-ttu-id="4683b-115">Get-CsServerApplication-Identity service: nom\<de domaine complet du pool: FQDN\></span><span class="sxs-lookup"><span data-stu-id="4683b-115">Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\></span></span>

<span data-ttu-id="4683b-116">Dans cette applet de \<demande,\> le nom de domaine complet (FQDN) du pool est le pool dans lequel l’application de conférence de routage basée sur l’emplacement doit être activée.</span><span class="sxs-lookup"><span data-stu-id="4683b-116">In this cmdlet, \<Pool FQDN\> is the pool in which the Location-Based Routing Conferencing application is to be enabled.</span></span>

<span data-ttu-id="4683b-117">Ce cmdlet renverra la liste des applications hébergées par Lync Server et la valeur Priority (priorité) pour chacune d’elles.</span><span class="sxs-lookup"><span data-stu-id="4683b-117">This cmdlet will return the list of the applications hosted by Lync Server and the priority value for each of them.</span></span> <span data-ttu-id="4683b-118">L’application de conférence de routage basée sur l’emplacement doit être affectée d’une valeur de priorité supérieure à l’application «UdcAgent» et plus petite que les applications «DefaultRouting», «ExumRouting» et «OutboundRouting».</span><span class="sxs-lookup"><span data-stu-id="4683b-118">The Location-Based Routing Conferencing application needs to be assigned a priority value larger than the “UdcAgent” application and smaller than the “DefaultRouting”, “ExumRouting” and “OutboundRouting” applications.</span></span> <span data-ttu-id="4683b-119">Nous vous recommandons d’affecter une valeur de priorité à l’application de conférence de routage basée sur l’emplacement, qui est un point supérieur à la valeur de priorité de l’application «UdcAgent».</span><span class="sxs-lookup"><span data-stu-id="4683b-119">We recommend that you assign the Location-Based Routing Conferencing application a priority value that is one point higher than the priority value of the “UdcAgent” application.</span></span>

<span data-ttu-id="4683b-120">Par exemple, si l’application «UdcAgent» a une valeur de priorité de «2», l’application «DefaultRouting» a une valeur de priorité de «8», l’application «ExumRouting» a une valeur de priorité de «9» et l’application «OutboundRouting» a une valeur de priorité de «10», alors vous devez attribuer une valeur de priorité de type «3» à l’application de conférence de routage basée sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="4683b-120">For example, if the “UdcAgent” application has a priority value of “2”, the “DefaultRouting” application has a priority value of “8”, the “ExumRouting” application has a priority value of “9” and the “OutboundRouting” application has a priority value of “10” then you should assign the Location-Based Routing Conferencing application a priority value of “3”.</span></span> <span data-ttu-id="4683b-121">Ainsi, la priorité des applications est définie dans l’ordre suivant : autres applications (priorités : 0 à 1), « UdcAgent » (priorité : 2), application de conférence avec routage géodépendant (priorité : 3), autres applications (priorités : 4 à 8), « DefaultRouting » (priorité : 9), « ExumRouting » (priorité : 10) et « OutboundRouting » (priorité : 11).</span><span class="sxs-lookup"><span data-stu-id="4683b-121">Doing so would place the priority of the applications in the following order: Other applications (Priorities: 0 to 1), “UdcAgent” (Priority: 2), Location-Based Routing Conferencing application (Priority: 3), other applications (Priorities: 4 to 8), “DefaultRouting” (Priority: 9), “ExumRouting” (Priority: 10) and “OutboundRouting” (Priority: 11).</span></span>

<span data-ttu-id="4683b-122">Une fois que vous avez trouvé la valeur de priorité correcte pour l’application de conférence de routage basée sur l’emplacement, tapez l’applet de commande suivante pour chaque pool frontal ou serveur Standard Edition sur lequel les utilisateurs ont activé le routage d’emplacement:</span><span class="sxs-lookup"><span data-stu-id="4683b-122">After you find the correct priority value for the Location-Based Routing Conferencing application, type the following cmdlet for each Front-End pool or Standard Edition Server that homes users enabled for Location-Based Routing:</span></span>

<span data-ttu-id="4683b-123">New-CsServerApplication-Identity service: Registrar\<: nom\>de domaine complet \<(FQDN\> )/LBRouting-Priority application Priority $true-URL critiques $truehttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="4683b-123">New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="4683b-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4683b-124">For example:</span></span>

<span data-ttu-id="4683b-125">New-CsServerApplication-Identity service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3 $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting</span><span class="sxs-lookup"><span data-stu-id="4683b-125">New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting</span></span>

<span data-ttu-id="4683b-126">Après avoir utilisé cette applet de demande, redémarrez tous les serveurs frontaux dans le pool ou les serveurs Standard Edition dans lesquels l’application de conférence de routage basée sur l’emplacement est activée.</span><span class="sxs-lookup"><span data-stu-id="4683b-126">After using this cmdlet, restart all Front End servers in the pool or the Standard Edition Servers where the Location-Based Routing Conferencing application has been enabled.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4683b-127">Les application de routage basées sur les emplacements aux conférences ou aux transferts de consultation ne seront pas appliquées tant que tous les serveurs frontaux dans les listes applicables ou les serveurs Standard Edition Server ne sont pas redémarrés.</span><span class="sxs-lookup"><span data-stu-id="4683b-127">Location-Based Routing enforcements to conferences or consultative transfers won’t be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted.</span></span>



</div>

<span data-ttu-id="4683b-128">Lorsque l’application de conférence de routage basée sur l’emplacement est activée et que tous les serveurs Lync en vigueur ont été redémarrés, toutes les conférences organisées par les utilisateurs de Lync activées pour le routage de l’emplacement seront surveillées pour éviter le contournement du numéro RTC</span><span class="sxs-lookup"><span data-stu-id="4683b-128">Once the Location-Based Routing Conferencing application has been successfully enabled and all applicable Lync servers have been restarted, all conferences organized by Lync users enabled for Location-Based Routing will be monitored to prevent PSTN toll bypass</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

