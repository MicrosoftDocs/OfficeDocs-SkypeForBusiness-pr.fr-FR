---
title: 'Lync Server 2013 : Configuration d’Enhanced 9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="92041-102">Configuration d’Enhanced 9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92041-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92041-103">_**Dernière modification de la rubrique:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="92041-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="92041-p101">Enhanced 9-1-1 (E9-1-1) est une fonctionnalité de notification d’urgence qui associe le numéro de téléphone de l’appelant à une adresse géographique ou postale. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="92041-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="92041-106">Pour prendre en charge E9-1-1, Lync Server 2013 doit être en mesure d’associer correctement un emplacement à un client et de s’assurer que ces informations sont utilisées pour diriger l’appel d’urgence vers le PSAPI le plus proche.</span><span class="sxs-lookup"><span data-stu-id="92041-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="92041-107">Pour plus d’informations sur la planification d’un déploiement E9-1-1, voir [planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="92041-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="92041-108">Lync Server 2013 ne prend en charge que E9-1-1 à l’intérieur des États-Unis.</span><span class="sxs-lookup"><span data-stu-id="92041-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="92041-109">Pour déployer E9-1-1, vous devez configurer une connexion SIP à un fournisseur de services E9-1-1 éligible ou déployer une passerelle ELIN (Emergency location identification) sur un fournisseur de services de téléphonie commutée (RTC) E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="92041-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="92041-110">Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) and Mediation Server dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="92041-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="92041-111">Pour plus d’informations sur la configuration des connexions de Trunk, voir <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">configurer une Trunk avec la dérivation multimédia dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="92041-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92041-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="92041-112">In This Section</span></span>

  - [<span data-ttu-id="92041-113">Configurer un itinéraire vocal E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92041-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="92041-114">Créer des stratégies d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92041-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="92041-115">Configurer les informations sur le site pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92041-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="92041-116">Configure the location database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92041-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="92041-117">Configurer les fonctionnalités avancées de E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92041-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

