---
title: 'Lync Server 2013 : gestion du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11cd9e2bb894f5fcb2230d08939d29852fba3fcd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="466c5-102">Gestion du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-102">Managing call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="466c5-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="466c5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="466c5-104">Le contrôle d’admission des appels détermine, en fonction de la bande passante réseau disponible, si des sessions de communication en temps réel, telles que des appels vocaux ou vidéo, peuvent être établies.</span><span class="sxs-lookup"><span data-stu-id="466c5-104">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="466c5-105">Utilisez les procédures suivantes pour gérer différentes fonctionnalités CAC pour votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="466c5-105">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="466c5-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="466c5-106">In This Section</span></span>

  - [<span data-ttu-id="466c5-107">Activation du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-107">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="466c5-108">Gestion des profils de stratégie de bande passante réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-108">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="466c5-109">Régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-109">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="466c5-110">Itinéraires de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-110">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="466c5-111">Contrôle d’admission des appels pour les sites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-111">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="466c5-112">Activation et désactivation de la contournement multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-112">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="466c5-113">Liaison des régions réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-113">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="466c5-114">Gestion des sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-114">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="466c5-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="466c5-115">See Also</span></span>


[<span data-ttu-id="466c5-116">Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466c5-116">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

