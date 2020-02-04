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
ms.openlocfilehash: 62f6858aa84309a268e8fc55af6cc0a63e6010a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="df60e-102">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df60e-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="df60e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="df60e-104">Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.</span><span class="sxs-lookup"><span data-stu-id="df60e-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="df60e-105">CAC contrôle le trafic en temps réel uniquement pour les appels audio et vidéo, et n’affecte pas le trafic des données.</span><span class="sxs-lookup"><span data-stu-id="df60e-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="df60e-106">Le CAC peut acheminer l’appel par le biais d’un chemin Internet lorsque le chemin de réseau étendu par défaut ne possède pas la bande passante requise.</span><span class="sxs-lookup"><span data-stu-id="df60e-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="df60e-107">Pour plus d’informations, reportez-vous à [planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df60e-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="df60e-108">Cette section fournit un ensemble d’exemples de procédures illustrant le déploiement et la gestion de CAC dans votre réseau.</span><span class="sxs-lookup"><span data-stu-id="df60e-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df60e-109">Avant de déployer le CAC, vous devez rassembler toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans l' <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">exemple ci-dessous pour rassembler vos exigences en matière de contrôle d’admission des appels dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="df60e-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="df60e-110">Veillez également à ce que les composants CAC aient été installés et activés, comme décrit dans la rubrique <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">définir et configurer un pool frontal ou un serveur Standard Edition dans Lync server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="df60e-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="df60e-111">Tous les exemples de déploiement et de gestion CAC dans cette section sont réalisés à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="df60e-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="df60e-112">En guise d’alternative, vous pouvez également utiliser la section <STRONG>Configuration réseau</STRONG> du panneau de configuration de Lync Server pour gérer CAC.</span><span class="sxs-lookup"><span data-stu-id="df60e-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df60e-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="df60e-113">In This Section</span></span>

  - [<span data-ttu-id="df60e-114">Configurer des régions réseau pour CAC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="df60e-115">Créer des profils de stratégie de bande passante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="df60e-116">Configurer les sites réseau pour le CAC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="df60e-117">Associez des sous-réseaux aux sites réseau pour le CAC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="df60e-118">Créer des liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="df60e-119">Créer des itinéraires réseau interrégion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="df60e-120">Créer des stratégies d’intersite réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="df60e-121">Activer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="df60e-122">Liste de contrôle du déploiement de contrôle d’admission des appels pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df60e-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

