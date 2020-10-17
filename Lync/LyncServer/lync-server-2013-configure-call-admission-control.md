---
title: 'Lync Server 2013 : configurer le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1edac7fe7b3b56cdaa5324f1c6e976bfb0b746fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517661"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="2985a-102">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-102">Configure call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2985a-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2985a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2985a-104">Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.</span><span class="sxs-lookup"><span data-stu-id="2985a-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="2985a-105">Il contrôle uniquement les contenus audio et vidéo du trafic en temps réel, et ne concerne pas le trafic des données.</span><span class="sxs-lookup"><span data-stu-id="2985a-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="2985a-106">Il peut acheminer l’appel via Internet lorsque la bande passante sur le chemin du réseau étendu par défaut est insuffisante.</span><span class="sxs-lookup"><span data-stu-id="2985a-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="2985a-107">Pour plus d’informations, reportez-vous à la rubrique [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="2985a-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="2985a-108">Cette section propose plusieurs exemples de procédures illustrant le déploiement et la gestion du contrôle d’admission des appels dans votre réseau.</span><span class="sxs-lookup"><span data-stu-id="2985a-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2985a-109">Avant de déployer le contrôle d’admission des appels, vous devez réunir toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans l' <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">exemple : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="2985a-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="2985a-110">Assurez-vous également que les composants CAC ont été installés et activés, comme décrit dans <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and Configure a front end pool or Standard Edition Server in Lync server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="2985a-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2985a-111">Tous les exemples de déploiement et de gestion CAC dans cette section sont exécutés à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2985a-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="2985a-112">En guise d’alternative, vous pouvez également utiliser la section <STRONG>Configuration réseau</STRONG> du panneau de configuration Lync Server pour gérer le contrôle d’admission des serveurs.</span><span class="sxs-lookup"><span data-stu-id="2985a-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2985a-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2985a-113">In This Section</span></span>

  - [<span data-ttu-id="2985a-114">Configuration des régions réseau pour le contrôle d’admission des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="2985a-115">Créer des profils de stratégie de bande passante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="2985a-116">Configuration des sites réseau pour le contrôle d’admission des adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="2985a-117">Associer des sous-réseaux à des sites réseau pour le contrôle d’admission des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="2985a-118">Créer des liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="2985a-119">Créer des itinéraires inter-région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="2985a-120">Créer des stratégies inter-sites réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="2985a-121">Activer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="2985a-122">Liste de vérification du déploiement du contrôle d’admission des appels pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2985a-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

