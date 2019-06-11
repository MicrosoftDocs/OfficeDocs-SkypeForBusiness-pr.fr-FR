---
title: 'Lync Server 2013: activation des utilisateurs pour E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d62d811d78695cbc04fa8def76da1843beddb586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="6abeb-102">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6abeb-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6abeb-103">_**Dernière modification de la rubrique:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="6abeb-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="6abeb-104">Lors de l’enregistrement du client, Lync Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6abeb-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="6abeb-105">Cette stratégie contient les paramètres qui déterminent la façon dont E9-1-1 est implémenté.</span><span class="sxs-lookup"><span data-stu-id="6abeb-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="6abeb-106">Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation d’urgence, et si un utilisateur est tenu d’entrer manuellement un emplacement si le service d’information d’emplacement n’en a pas fourni automatiquement un.</span><span class="sxs-lookup"><span data-stu-id="6abeb-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="6abeb-107">Pour obtenir une définition complète d’une stratégie d’emplacement, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6abeb-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="6abeb-108">Lync Server peut affecter une stratégie d’emplacement aux clients en fonction du sous-réseau, ou à des utilisateurs basés sur une stratégie globale, par site ou par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6abeb-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="6abeb-109">Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="6abeb-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="6abeb-110">**Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**</span><span class="sxs-lookup"><span data-stu-id="6abeb-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="6abeb-111">Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale.</span><span class="sxs-lookup"><span data-stu-id="6abeb-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="6abeb-112">Toutefois, en assignant une stratégie d’emplacement à un site réseau du serveur Lync et en ajoutant des sous-réseaux au site, vous pouvez limiter le support de E9-1-1 à des emplacements sélectionnés au sein de l’entreprise et spécifier le comportement de routage de E9-1-1 pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="6abeb-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="6abeb-113">**Envisagez-vous d’activer des utilisateurs individuels par le biais d’une stratégie utilisateur ?**</span><span class="sxs-lookup"><span data-stu-id="6abeb-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="6abeb-114">Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.</span><span class="sxs-lookup"><span data-stu-id="6abeb-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="6abeb-115">**Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, doivent-ils bénéficier du service E9-1-1 ?**</span><span class="sxs-lookup"><span data-stu-id="6abeb-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="6abeb-116">Si des utilisateurs se voient attribuer une stratégie d’emplacement globale, de site ou par utilisateur, ils peuvent être obligés d’entrer manuellement un emplacement dans le client si le client ne se trouve pas dans un sous-réseau défini ou s’il n’y a pas de localisation trouvée par le service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="6abeb-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="6abeb-117">Pour plus d’informations, reportez-vous à [définition de l’interface utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="6abeb-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

