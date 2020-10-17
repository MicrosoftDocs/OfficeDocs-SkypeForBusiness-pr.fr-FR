---
title: 'Lync Server 2013 : déploiement des serveurs de médiation et définition des homologues'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b22a232bd304d4db3faae168f42dae11cea8fc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507381"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="9925e-102">Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9925e-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9925e-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9925e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9925e-104">La charge de travail voix entreprise, les conférences rendez-vous et les applications avancées de voix entreprise (application Response Group, application de parcage d’appel, contrôle d’admission des appels (CAC), etc.) sont disponibles dans les pools frontaux.</span><span class="sxs-lookup"><span data-stu-id="9925e-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="9925e-105">Avec Lync Server 2013, la fonctionnalité du serveur de médiation est intégrée au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="9925e-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="9925e-106">Un serveur de médiation autonome distinct n’est plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="9925e-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="9925e-107">Les pools frontaux peuvent communiquer directement avec les passerelles prises en charge (une passerelle RTC (réseau téléphonique commuté) ou un IP-PBX), ce qui élimine la nécessité d’un serveur de médiation comme intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="9925e-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="9925e-108">La seule exception est si vous configurez une jonction SIP pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="9925e-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="9925e-109">Pour connecter votre infrastructure voix entreprise à votre fournisseur de jonction SIP, un serveur de médiation distinct doit être déployé.</span><span class="sxs-lookup"><span data-stu-id="9925e-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="9925e-110">La connexion entre Lync Server (le composant serveur de médiation sur un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée *jonction*.</span><span class="sxs-lookup"><span data-stu-id="9925e-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="9925e-111">Les rubriques de cette section décrivent comment définir une jonction et déployer un serveur de médiation autonome, si vous vous connectez à une jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="9925e-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9925e-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9925e-112">In This Section</span></span>

  - [<span data-ttu-id="9925e-113">Définition d’un serveur de médiation dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9925e-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="9925e-114">Définition d’une passerelle dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9925e-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="9925e-115">Installer les fichiers pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9925e-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="9925e-116">Définir d’autres jonctions dans le générateur de topologies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9925e-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9925e-117">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="9925e-117">Related Sections</span></span>

[<span data-ttu-id="9925e-118">Configuration de la Conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9925e-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

