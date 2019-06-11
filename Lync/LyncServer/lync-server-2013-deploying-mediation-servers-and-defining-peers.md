---
title: 'Lync Server 2013 : Déploiement des serveurs de médiation et définition des homologues'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01ccf2e3822933842249df012877b13d10baef3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="09fde-102">Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09fde-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09fde-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="09fde-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="09fde-104">La charge de travail voix entreprise, les conférences rendez-vous et les applications Advanced Enterprise voix (application de groupe de réponse, application de stationnement d’appel, contrôle d’admission des appels (CAC), etc.), sont disponibles dans des regroupements front-end.</span><span class="sxs-lookup"><span data-stu-id="09fde-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="09fde-105">Avec Lync Server 2013, les fonctionnalités du serveur de médiation sont intégrées au serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="09fde-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="09fde-106">Un serveur de médiation autonome distinct n’est plus nécessaire.</span><span class="sxs-lookup"><span data-stu-id="09fde-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="09fde-107">Les pools front-end peuvent communiquer directement avec les passerelles prises en charge (une passerelle RTC (réseau téléphonique commuté) ou un PBX IP (PBX), ce qui évite qu’un serveur de médiation ne serve de intermédiaire.</span><span class="sxs-lookup"><span data-stu-id="09fde-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="09fde-108">La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="09fde-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="09fde-109">Pour connecter l’infrastructure vocale de votre entreprise à votre fournisseur SIP Trunk, un serveur de médiation distinct doit être déployé.</span><span class="sxs-lookup"><span data-stu-id="09fde-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="09fde-110">La connexion entre Lync Server (le composant du serveur de médiation sur une liste frontale ou un serveur de médiation autonome) et une passerelle est définie en tant qu’association logique appelée *Trunk*.</span><span class="sxs-lookup"><span data-stu-id="09fde-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="09fde-111">Les rubriques de cette section expliquent comment définir un élément Trunk et comment déployer un serveur de médiation autonome si vous vous connectez à un Trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="09fde-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09fde-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="09fde-112">In This Section</span></span>

  - [<span data-ttu-id="09fde-113">Définir un serveur de médiation dans le générateur de topologies de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09fde-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="09fde-114">Définir une passerelle dans le générateur de topologies de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09fde-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="09fde-115">Installer les fichiers pour le serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09fde-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="09fde-116">Définir des lignes supplémentaires dans le générateur de topologies de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09fde-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="09fde-117">Sections associées</span><span class="sxs-lookup"><span data-stu-id="09fde-117">Related Sections</span></span>

[<span data-ttu-id="09fde-118">Configuration de conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09fde-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

