---
title: 'Lync Server 2013 : À propos des régions réseau, des sites réseau et des sous-réseaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="9781d-102">À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9781d-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9781d-103">_**Dernière modification de la rubrique:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9781d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9781d-104">Les fonctionnalités avancées de voix entreprise décrites dans cette section partagent certaines exigences de configuration pour les zones réseau, les sites réseau et les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="9781d-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="9781d-105">Par exemple, les trois fonctionnalités avancées nécessitent que chaque sous-réseau de votre topologie soit associé à un *site réseau*spécifique et chaque site réseau doit être associé à une *région réseau*.</span><span class="sxs-lookup"><span data-stu-id="9781d-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9781d-106">Avant de commencer la configuration du réseau pour le contrôle d’admission des appels, E9-1-1 ou le contournement multimédia, assurez-vous d’avoir examiné les informations supplémentaires sur les paramètres réseau dans les <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">paramètres réseau pour les fonctionnalités avancées d’Enterprise voix dans Lync Server 2013</A> section de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="9781d-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="9781d-107">Pour plus d’informations sur la configuration du réseau essentiellement sur le contrôle d’admission des appels, voir <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">définir vos exigences de contrôle d’admission des appels dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="9781d-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="9781d-108">Le contrôle d’admission des appels et E9-1-1 ont des exigences de configuration supplémentaires pour les sites réseau :</span><span class="sxs-lookup"><span data-stu-id="9781d-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="9781d-109">Le contrôle d’admission des appels nécessite de spécifier un *profil de stratégie de bande passante* pour chaque site soumis à des restrictions de bande passante de réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="9781d-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="9781d-110">Si vous envisagez de déployer le contrôle d’admission des appels, vous devez [créer des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) avant de configurer les sites de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="9781d-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="9781d-111">E9-1-1 nécessite de spécifier une *stratégie d’emplacement* pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="9781d-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="9781d-112">Si vous envisagez de déployer E9-1-1, vous devez [créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md) avant de configurer les sites de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="9781d-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="9781d-113">Créer ou modifier des régions, des sites et des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="9781d-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="9781d-114">Les rubriques suivantes décrivent les étapes permettant de créer ou de modifier des zones et des sites réseau, et d’associer des sous-réseaux aux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="9781d-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="9781d-115">Ces rubriques ne sont pas spécifiques à toutes les fonctionnalités avancées de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="9781d-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="9781d-116">Créer ou modifier une région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9781d-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="9781d-117">Création ou modification d’un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9781d-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="9781d-118">Association d’un sous-réseau à un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9781d-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

