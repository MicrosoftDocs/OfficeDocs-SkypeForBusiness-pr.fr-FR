---
title: 'Lync Server 2013 : fonctionnalités de résistance de site de succursale'
description: 'Lync Server 2013 : fonctionnalités de résistance de site de succursale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552200"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="fce7c-103">Fonctionnalités de résistance de site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7c-103">Branch-site resiliency features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fce7c-104">_**Dernière modification de la rubrique :** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="fce7c-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="fce7c-105">Si vous fournissez la résistance des sites de succursale et que la connexion WAN d’un site de succursale à un site central échoue si ce dernier est inaccessible, les fonctionnalités vocales suivantes seront encore disponibles :</span><span class="sxs-lookup"><span data-stu-id="fce7c-105">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="fce7c-106">Appels PSTN entrants et sortants</span><span class="sxs-lookup"><span data-stu-id="fce7c-106">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="fce7c-107">Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents</span><span class="sxs-lookup"><span data-stu-id="fce7c-107">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="fce7c-108">Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert</span><span class="sxs-lookup"><span data-stu-id="fce7c-108">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="fce7c-109">Messagerie instantanée entre deux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fce7c-109">Two-party instant messaging</span></span>

  - <span data-ttu-id="fce7c-110">Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si le délégant et le délégué (par exemple, un responsable et l’administrateur de ce dernier), ou tous les membres de l’équipe, sont configurés sur le même site.</span><span class="sxs-lookup"><span data-stu-id="fce7c-110">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="fce7c-111">Enregistrements des détails des appels (CDR)</span><span class="sxs-lookup"><span data-stu-id="fce7c-111">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="fce7c-112">Conférence rendez-vous par réseau téléphonique commuté (PSTN) avec standard automatique de conférence</span><span class="sxs-lookup"><span data-stu-id="fce7c-112">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="fce7c-113">Les fonctionnalités de messagerie vocale, si vous configurez les paramètres de réacheminement de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="fce7c-113">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="fce7c-114">(Pour plus d’informations, consultez la rubrique [Configuration requise pour la résistance des sites de succursale pour Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span><span class="sxs-lookup"><span data-stu-id="fce7c-114">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="fce7c-115">Authentification et autorisations des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="fce7c-115">User authentication and authorization</span></span>

<span data-ttu-id="fce7c-116">Les fonctionnalités suivantes seront disponibles uniquement si votre solution de résilience est un déploiement Lync Server complet sur le site de succursale :</span><span class="sxs-lookup"><span data-stu-id="fce7c-116">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="fce7c-117">messagerie instantanée, conférence A/V et web</span><span class="sxs-lookup"><span data-stu-id="fce7c-117">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="fce7c-118">routage basé sur la présence et Ne pas déranger (DND (quand les appels ne sonnent pas sur les postes dont le statut est Ne pas déranger)</span><span class="sxs-lookup"><span data-stu-id="fce7c-118">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="fce7c-119">Mise à jour des paramètres de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="fce7c-119">Updating call forwarding settings</span></span>

  - <span data-ttu-id="fce7c-120">Application Response Group et application parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="fce7c-120">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="fce7c-121">Mise en service des nouveaux téléphones et clients, mais uniquement si les services de domaine Active Directory sont présents sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="fce7c-121">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="fce7c-122">Enhanced 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="fce7c-122">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="fce7c-123">Si E9-1-1 est déployé et que la jonction SIP sur le site central n’est pas disponible car la liaison de réseau étendu est inactive, le Survivable Branch Appliance achemine les appels E9-1-1 vers la passerelle de succursale locale.</span><span class="sxs-lookup"><span data-stu-id="fce7c-123">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="fce7c-124">Pour activer cette fonctionnalité, les stratégies de voix des utilisateurs du site de succursale doivent acheminer les appels vers la passerelle locale en cas de panne du réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="fce7c-124">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fce7c-125">SBA (Survivable Branch Office) n’est pas pris en charge pour XMPP.</span><span class="sxs-lookup"><span data-stu-id="fce7c-125">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="fce7c-126">Les utilisateurs hébergés dans une configuration SBA ne peuvent pas envoyer de messages instantanés ou voir la présence avec des contacts XMPP.</span><span class="sxs-lookup"><span data-stu-id="fce7c-126">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

