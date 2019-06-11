---
title: 'Lync Server 2013 : Prise en charge des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b264abefb1234892df355fee123dd6ce68b4dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a><span data-ttu-id="0d0fc-102">Prise en charge des services de domaine Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d0fc-102">Active Directory Domain Services support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d0fc-103">_**Dernière modification de la rubrique:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0d0fc-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0d0fc-104">Lync Server 2013 utilise le magasin central de gestion pour stocker les données de configuration pour les serveurs et les services, au lieu de s’appuyer sur les services de domaine Active Directory (AD FS) pour ces informations, comme précédemment.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-104">Lync Server 2013 uses the Central Management store to store configuration data for servers and services, instead of relying on Active Directory Domain Services for this information, as in the past.</span></span> <span data-ttu-id="0d0fc-105">Lync Server 2013 enregistre toujours les éléments suivants dans AD DS:</span><span class="sxs-lookup"><span data-stu-id="0d0fc-105">Lync Server 2013 still stores the following in AD DS:</span></span>

  - <span data-ttu-id="0d0fc-106">**Extensions de schéma**</span><span class="sxs-lookup"><span data-stu-id="0d0fc-106">**Schema extensions**</span></span>
    
      - <span data-ttu-id="0d0fc-107">Extensions de l’objet utilisateur</span><span class="sxs-lookup"><span data-stu-id="0d0fc-107">User object extensions</span></span>
    
      - <span data-ttu-id="0d0fc-108">Extensions pour les classes Lync Server 2010 et Office Communications Server 2007 R2 pour garantir la compatibilité descendante avec les versions prises en charge précédentes</span><span class="sxs-lookup"><span data-stu-id="0d0fc-108">Extensions for Lync Server 2010 and Office Communications Server 2007 R2 classes to maintain backward compatibility with previous supported versions</span></span>

  - <span data-ttu-id="0d0fc-109">**Data (données** ) (stocké dans le schéma étendu de Lync Server 2013 et dans les classes existantes)</span><span class="sxs-lookup"><span data-stu-id="0d0fc-109">**Data** (stored in Lync Server 2013 extended schema and in existing classes)</span></span>
    
      - <span data-ttu-id="0d0fc-110">URI SIP de l’utilisateur et autres paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="0d0fc-110">User SIP URI and other user settings</span></span>
    
      - <span data-ttu-id="0d0fc-111">Objets de contact pour applications (par exemple, l’application Response Group et l’application attendant);</span><span class="sxs-lookup"><span data-stu-id="0d0fc-111">Contact objects for applications (for example, the Response Group application and the Conferencing Attendant application)</span></span>
    
      - <span data-ttu-id="0d0fc-112">Données publiées pour la compatibilité descendante</span><span class="sxs-lookup"><span data-stu-id="0d0fc-112">Data published for backward compatibility</span></span>
    
      - <span data-ttu-id="0d0fc-113">Un point de contrôle de service (SCP) pour le magasin de gestion central</span><span class="sxs-lookup"><span data-stu-id="0d0fc-113">A service control point (SCP) for the Central Management store</span></span>
    
      - <span data-ttu-id="0d0fc-114">Compte d’authentification Kerberos (objet facultatif de l’ordinateur)</span><span class="sxs-lookup"><span data-stu-id="0d0fc-114">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="0d0fc-115">Cette section décrit la configuration requise pour la prise en charge des services d’annuaire Active Directory pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-115">This section describes the AD DS support requirements for Lync Server 2013.</span></span> <span data-ttu-id="0d0fc-116">Pour plus d’informations sur la prise en charge de la topologie, voir [topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation relative à la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-116">For details about topology support, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span>

<div>

## <a name="supported-domain-controller-operating-systems"></a><span data-ttu-id="0d0fc-117">Systèmes d’exploitation de contrôleur de domaine pris en charge</span><span class="sxs-lookup"><span data-stu-id="0d0fc-117">Supported Domain Controller Operating Systems</span></span>

<span data-ttu-id="0d0fc-118">Lync Server 2013 prend en charge les contrôleurs de domaine exécutant les systèmes d’exploitation suivants:</span><span class="sxs-lookup"><span data-stu-id="0d0fc-118">Lync Server 2013 supports domain controllers running the following operating systems:</span></span>

  - <span data-ttu-id="0d0fc-119">Système d’exploitation Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0d0fc-119">Windows Server 2012 R2 operating system</span></span>

  - <span data-ttu-id="0d0fc-120">Système d’exploitation Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0d0fc-120">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="0d0fc-121">Système d’exploitation Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0d0fc-121">Windows Server 2008 R2 operating system</span></span>

  - <span data-ttu-id="0d0fc-122">Système d’exploitation Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="0d0fc-122">Windows Server 2008 operating system</span></span>

  - <span data-ttu-id="0d0fc-123">Windows Server 2008 entreprise 32 bits</span><span class="sxs-lookup"><span data-stu-id="0d0fc-123">Windows Server 2008 Enterprise 32-Bit</span></span>

  - <span data-ttu-id="0d0fc-124">Versions 32 ou 64 bits du système d’exploitation Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="0d0fc-124">The 32-bit or 64-bit versions of the Window Server 2003 R2 operating system</span></span>

  - <span data-ttu-id="0d0fc-125">Versions 32 ou 64 bits du système d’exploitation Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="0d0fc-125">The 32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

</div>

<div>

## <a name="forest-and-domain-functional-level"></a><span data-ttu-id="0d0fc-126">Niveau fonctionnel de la forêt et du domaine</span><span class="sxs-lookup"><span data-stu-id="0d0fc-126">Forest and Domain Functional Level</span></span>

<span data-ttu-id="0d0fc-127">Vous devez déclencher tous les domaines dans lesquels vous déployez Lync Server 2013 vers un niveau de fonctionnement du domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-127">You must raise all domains in which you deploy Lync Server 2013 to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

<span data-ttu-id="0d0fc-128">Toutes les forêts dans lesquelles vous déployez Lync Server 2013 doivent être déclenchées à un niveau de fonctionnalité de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-128">All forests in which you deploy Lync Server 2013 must be raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a><span data-ttu-id="0d0fc-129">Prise en charge des contrôleurs de domaine en lecture seule</span><span class="sxs-lookup"><span data-stu-id="0d0fc-129">Support for Read-Only Domain Controllers</span></span>

<span data-ttu-id="0d0fc-130">Lync Server 2013 prend en charge les déploiements des services de domaine Active Directory (AD FS) qui incluent des contrôleurs de domaine en lecture seule ou des serveurs de catalogue global en lecture seule, tant qu’il existe des contrôleurs de domaine accessibles en écriture.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-130">Lync Server 2013 supports Active Directory Domain Services deployments that include read-only domain controllers or read-only global catalog servers, as long as there are writable domain controllers available.</span></span>

</div>

<div>

## <a name="domain-names"></a><span data-ttu-id="0d0fc-131">Noms de domaine</span><span class="sxs-lookup"><span data-stu-id="0d0fc-131">Domain Names</span></span>

<span data-ttu-id="0d0fc-132">Le serveur Lync ne prend pas en charge les domaines à étiquette unique.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-132">Lync Server does not support single-labeled domains.</span></span> <span data-ttu-id="0d0fc-133">Par exemple, une forêt avec un domaine racine appelé **contoso. local** est prise en charge, mais un domaine racine nommé **local** n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-133">For example, a forest with a root domain named **contoso.local** is supported, but a root domain named **local** is not supported.</span></span> <span data-ttu-id="0d0fc-134">Pour plus d’informations, reportez-vous à l’article 300684 de la base de connaissances Microsoft, intitulé «informations sur la configuration [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)de Windows pour les domaines avec des noms DNS en une seule étiquette».</span><span class="sxs-lookup"><span data-stu-id="0d0fc-134">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d0fc-135">Le serveur Lync ne prend pas en charge le changement de nom de domaines.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-135">Lync Server does not support renaming domains.</span></span> <span data-ttu-id="0d0fc-136">Si vous avez besoin de renommer un domaine sur lequel Lync Server est déployé, vous devez commencer par désinstaller Lync Server, puis renommer le domaine, puis réinstaller Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-136">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a><span data-ttu-id="0d0fc-137">Environnements AD DS verrouillés</span><span class="sxs-lookup"><span data-stu-id="0d0fc-137">Locked Down AD DS Environments</span></span>

<span data-ttu-id="0d0fc-138">Dans un environnement AD DS verrouillé, les utilisateurs et les objets ordinateur sont souvent placés dans des unités d’organisation (UO) spécifiques avec l’héritage des autorisations désactivé pour sécuriser la délégation d’administration et permettre l’utilisation des objets de stratégie de groupe pour l’application. stratégies de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-138">In a locked-down AD DS environment, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span> <span data-ttu-id="0d0fc-139">Lync Server 2013 peut être déployé dans un environnement Active Directory verrouillé.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-139">Lync Server 2013 can be deployed in a locked-down Active Directory environment.</span></span> <span data-ttu-id="0d0fc-140">Pour plus d’informations sur les éléments requis pour déployer Lync Server dans un environnement verrouillé, voir [préparer un service de domaine Active Directory (AD FS) verrouillé dans Lync server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0d0fc-140">For details about what is required to deploy Lync Server in a locked-down environment, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

