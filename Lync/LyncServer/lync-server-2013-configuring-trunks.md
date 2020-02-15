---
title: 'Lync Server 2013 : configuration des jonctions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 123535ae3e14669e343c881869304e95ce666040
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="85196-102">Configuration des jonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85196-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="85196-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="85196-104">Dans le cadre du déploiement de voix entreprise, vous pouvez configurer une jonction entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et les appareils voix entreprise de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="85196-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="85196-105">Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet</span><span class="sxs-lookup"><span data-stu-id="85196-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="85196-106">Passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="85196-106">PSTN gateway</span></span>

  - <span data-ttu-id="85196-107">Autocommutateur privé (PBX)</span><span class="sxs-lookup"><span data-stu-id="85196-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="85196-108">Pour plus d’informations, reportez-vous à la rubrique [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="85196-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="85196-109">Avant de commencer la configuration des jonctions, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés l’un à l’autre.</span><span class="sxs-lookup"><span data-stu-id="85196-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="85196-110">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">définition d’une passerelle dans le générateur de topologie dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="85196-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="85196-111">Dans le cadre de la configuration de jonction, vous pouvez activer la fonctionnalité de contournement de média Lync Server 2013, qui permet aux médias de contourner le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="85196-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="85196-112">Vous pouvez configurer les jonctions sans activer le contournement de média mais nous vous conseillons vivement de l’activer.</span><span class="sxs-lookup"><span data-stu-id="85196-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="85196-113">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="85196-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85196-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="85196-114">In This Section</span></span>

  - [<span data-ttu-id="85196-115">Prise en charge de plusieurs tronçons dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="85196-116">Routage entre les jonctions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="85196-117">Afficher les informations de configuration de jonction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="85196-118">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="85196-119">Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="85196-120">Créer une collection de paramètres de configuration de jonction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="85196-121">Supprimer une collection existante de paramètres de configuration de jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="85196-122">Modifier les paramètres de configuration de jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="85196-123">Tester les paramètres de configuration de jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="85196-124">Afficher des informations sur les jonctions SIP individuelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85196-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85196-125">See Also</span></span>


[<span data-ttu-id="85196-126">Définition d’une passerelle dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="85196-127">Planification de la connectivité PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="85196-128">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85196-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

