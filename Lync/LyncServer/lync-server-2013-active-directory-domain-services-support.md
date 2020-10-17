---
title: 'Lync Server 2013 : prise en charge des services de domaine Active Directory'
description: 'Lync Server 2013 : prise en charge des services de domaine Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558680"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="3d3df-103">Prise en charge des services de domaine Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d3df-103">Active Directory Domain Services support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d3df-104">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="3d3df-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="3d3df-105">Lync Server 2013 utilise le magasin central de gestion pour stocker les données de configuration des serveurs et des services, au lieu de s’appuyer sur les services de domaine Active Directory pour ces informations, comme dans le passé.</span><span class="sxs-lookup"><span data-stu-id="3d3df-105">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="3d3df-106">Lync Server 2013 stocke toujours les éléments suivants dans AD DS :</span><span class="sxs-lookup"><span data-stu-id="3d3df-106">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="3d3df-107">**Extensions de schéma**</span><span class="sxs-lookup"><span data-stu-id="3d3df-107">**Schema extensions**</span></span>
    
      - <span data-ttu-id="3d3df-108">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="3d3df-108">User object extensions</span></span>
    
      - <span data-ttu-id="3d3df-109">Extensions pour les classes Lync Server 2010 et Office Communications Server 2007 R2 afin de maintenir la compatibilité descendante avec les versions prises en charge précédentes</span><span class="sxs-lookup"><span data-stu-id="3d3df-109">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="3d3df-110">**Données** (stockées dans le schéma étendu Lync Server 2013 et dans les classes existantes)</span><span class="sxs-lookup"><span data-stu-id="3d3df-110">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="3d3df-111">URI SIP de l’utilisateur et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="3d3df-111">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="3d3df-112">Objets contact pour les applications (par exemple, l’application Response Group et l’application de surveillance de conférence)</span><span class="sxs-lookup"><span data-stu-id="3d3df-112">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="3d3df-113">Données publiées pour la compatibilité descendante</span><span class="sxs-lookup"><span data-stu-id="3d3df-113">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="3d3df-114">Un point de contrôle de service (SCP) pour le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="3d3df-114">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="3d3df-115">Compte d’authentification Kerberos (un objet ordinateur facultatif)</span><span class="sxs-lookup"><span data-stu-id="3d3df-115">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="3d3df-116">Cette section décrit la configuration requise pour la prise en charge des services AD DS pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d3df-116">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="3d3df-117">Pour plus d’informations sur la prise en charge de la topologie, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="3d3df-117">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="3d3df-118">Systèmes d’exploitation de contrôleur de domaine pris en charge</span><span class="sxs-lookup"><span data-stu-id="3d3df-118">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="3d3df-119">Lync Server 2013 prend en charge les contrôleurs de domaine exécutant les systèmes d’exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="3d3df-119">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="3d3df-120">Système d’exploitation Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3d3df-120">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="3d3df-121">Système d’exploitation Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3d3df-121">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="3d3df-122">système d’exploitation Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="3d3df-122">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="3d3df-123">système d’exploitation Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="3d3df-123">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="3d3df-124">Windows Server 2008 Enterprise 32 bits</span><span class="sxs-lookup"><span data-stu-id="3d3df-124">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="3d3df-125">Les versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="3d3df-125">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="3d3df-126">Les versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="3d3df-126">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="3d3df-127">Niveau fonctionnel de la forêt et du domaine</span><span class="sxs-lookup"><span data-stu-id="3d3df-127">Forest and Domain Functional Level</span></span>

<span data-ttu-id="3d3df-128">Vous devez déclencher tous les domaines dans lesquels vous déployez Lync Server 2013 sur un niveau fonctionnel de domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="3d3df-128">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="3d3df-129">Toutes les forêts dans lesquelles vous déployez Lync Server 2013 doivent être augmentées jusqu’à un niveau fonctionnel de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au moins Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="3d3df-129">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="3d3df-130">Prise en charge des contrôleurs de domaine Read-Only</span><span class="sxs-lookup"><span data-stu-id="3d3df-130">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="3d3df-131">Lync Server 2013 prend en charge les déploiements des services de domaine Active Directory qui incluent des contrôleurs de domaine en lecture seule ou des serveurs de catalogue global en lecture seule, à condition qu’il y ait des contrôleurs de domaine accessibles en écriture.</span><span class="sxs-lookup"><span data-stu-id="3d3df-131">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="3d3df-132">Noms de domaine</span><span class="sxs-lookup"><span data-stu-id="3d3df-132">Domain Names</span></span>

<span data-ttu-id="3d3df-133">Lync Server ne prend pas en charge les domaines à étiquette unique.</span><span class="sxs-lookup"><span data-stu-id="3d3df-133">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="3d3df-134">Par exemple, une forêt comportant le domaine racine **contoso.local** est prise en charge alors que le domaine racine **local** ne l’est pas.</span><span class="sxs-lookup"><span data-stu-id="3d3df-134">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="3d3df-135">Pour plus d’informations, consultez l’article 300684 de la base de connaissances Microsoft, « informations sur la configuration de Windows pour les domaines avec des noms DNS en une seule partie », à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) .</span><span class="sxs-lookup"><span data-stu-id="3d3df-135">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d3df-136">Lync Server ne prend pas en charge le changement de nom des domaines.</span><span class="sxs-lookup"><span data-stu-id="3d3df-136">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="3d3df-137">Si vous devez renommer un domaine où Lync Server est déployé, vous devez d’abord désinstaller Lync Server, renommer le domaine, puis réinstaller Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d3df-137">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="3d3df-138">Environnements AD DS verrouillés</span><span class="sxs-lookup"><span data-stu-id="3d3df-138">Locked Down AD DS Environments</span></span>

<span data-ttu-id="3d3df-139">Dans un environnement AD DS verrouillé, les utilisateurs et les objets ordinateur sont souvent placés dans des unités d’organisation (UO) spécifiques dont l’héritage des autorisations est désactivé pour aider à sécuriser la délégation d’administration et pour permettre l’utilisation des objets de stratégie de groupe (GPO) pour appliquer des stratégies de sécurité.</span><span class="sxs-lookup"><span data-stu-id="3d3df-139">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="3d3df-140">Lync Server 2013 peut être déployé dans un environnement Active Directory verrouillé.</span><span class="sxs-lookup"><span data-stu-id="3d3df-140">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="3d3df-141">Pour plus d’informations sur les éléments requis pour déployer Lync Server dans un environnement verrouillé, voir [Preparing a Locked Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="3d3df-141">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

