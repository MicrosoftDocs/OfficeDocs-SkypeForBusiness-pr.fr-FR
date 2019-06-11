---
title: 'Lync Server 2013 : Configuration des jonctions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d40a290f75ae48b73a4695e04ea2934b0c4d695
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="c623d-102">Configuration des jonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c623d-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c623d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c623d-104">Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques vocaux d’entreprise au sein de votre organisation:</span><span class="sxs-lookup"><span data-stu-id="c623d-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="c623d-105">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="c623d-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="c623d-106">Passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="c623d-106">PSTN gateway</span></span>

  - <span data-ttu-id="c623d-107">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="c623d-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="c623d-108">Pour plus d’informations, reportez-vous à [planification de la connectivité PSTN dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c623d-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c623d-109">Avant de commencer la configuration de Trunk, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés entre eux.</span><span class="sxs-lookup"><span data-stu-id="c623d-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="c623d-110">Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">définir une passerelle dans le générateur de topologie de Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c623d-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c623d-111">Dans le cadre de la configuration de Trunk, vous pouvez activer la fonctionnalité de contournement de média Lync Server 2013, qui permet aux éléments multimédias d’ignorer le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c623d-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="c623d-112">Les Trunks peuvent être configurés avec ou sans Bypass multimédia activé, mais nous vous recommandons vivement de l’activer.</span><span class="sxs-lookup"><span data-stu-id="c623d-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="c623d-113">Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-planning-for-media-bypass.md">planification de la dérivation multimédia dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="c623d-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c623d-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c623d-114">In This Section</span></span>

  - [<span data-ttu-id="c623d-115">Prise en charge de plusieurs Trunks dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="c623d-116">Routage inter-Trunk dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="c623d-117">Afficher les informations de configuration de Trunk dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="c623d-118">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="c623d-119">Configurer un Trunk sans dérivation multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="c623d-120">Créer une collection de paramètres de configuration de Trunk dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="c623d-121">Supprimer une collection existante de paramètres de configuration de Trunk SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c623d-122">Modifier les paramètres de configuration de Trunk SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c623d-123">Tester les paramètres de configuration du Trunk SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="c623d-124">Afficher des informations sur les lignes SIP individuelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c623d-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c623d-125">See Also</span></span>


[<span data-ttu-id="c623d-126">Définir une passerelle dans le générateur de topologies de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="c623d-127">Planification de la connectivité PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="c623d-128">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c623d-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

