---
title: 'Lync Server 2013 : configurer Enhanced 9-1-1'
description: 'Lync Server 2013 : configurer Enhanced 9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553330"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="269e1-103">Configurer Enhanced 9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="269e1-103">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="269e1-104">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="269e1-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="269e1-p101">Enhanced 9-1-1 (E9-1-1) est une fonctionnalité de notification d’urgence qui associe le numéro de téléphone de l’appelant à une adresse géographique ou postale. Au moyen de ces informations, le centre d’appels de la sécurité publique (PSAP) peut immédiatement contacter les services d’urgence et les dépêcher sur place pour porter secours à l’appelant.</span><span class="sxs-lookup"><span data-stu-id="269e1-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="269e1-107">Pour prendre en charge E9-1-1, Lync Server 2013 doit être en mesure d’associer correctement un emplacement à un client et de s’assurer que ces informations sont utilisées pour acheminer l’appel d’urgence vers le PSAPI le plus proche.</span><span class="sxs-lookup"><span data-stu-id="269e1-107">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="269e1-108">Pour plus d’informations sur la planification d’un déploiement E9-1-1, reportez-vous à la rubrique [Planning for Emergency Services (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="269e1-108">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="269e1-109">Lync Server 2013 prend uniquement en charge E9-1-1 aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="269e1-109">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="269e1-110">Pour déployer E9-1-1, vous devez configurer une connexion SIP à un fournisseur de services E9-1-1 certifié, ou déployer une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 basé sur le réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="269e1-110">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="269e1-111">Pour plus d’informations, voir <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">enhanced 9-1-1 (E9-1-1) et serveur de médiation dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="269e1-111">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="269e1-112">Pour plus d’informations sur la configuration des connexions de jonction, voir <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with Media Bypass in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="269e1-112">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="269e1-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="269e1-113">In This Section</span></span>

  - [<span data-ttu-id="269e1-114">Configuration d’un itinéraire des communications vocales E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="269e1-114">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="269e1-115">Créer des stratégies d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="269e1-115">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="269e1-116">Configurer les informations de site pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="269e1-116">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="269e1-117">Configuration de la base de données d’emplacements dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="269e1-117">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="269e1-118">Configurer les fonctionnalités avancées d’E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="269e1-118">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

