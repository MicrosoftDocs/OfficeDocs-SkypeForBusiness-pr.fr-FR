---
title: 'Lync Server 2013: planification des déploiements hybrides'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b528e22e24635d47755096cd4bf81d4066feb3c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="592ff-102">Planification des déploiements hybrides de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="592ff-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="592ff-103">_**Dernière modification de la rubrique:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="592ff-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="592ff-104">Prenez en compte les exigences suivantes pour les utilisateurs et votre infrastructure réseau lors de la planification d’un déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="592ff-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="592ff-105">Exigences d’infrastructure</span><span class="sxs-lookup"><span data-stu-id="592ff-105">Infrastructure Requirements</span></span>

<span data-ttu-id="592ff-106">Pour pouvoir implémenter et déployer un déploiement hybride, vous devez disposer des éléments suivants configurés dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="592ff-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="592ff-107">Un client Microsoft Office 365 doté de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="592ff-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="592ff-108">Notez que vous pouvez uniquement utiliser un seul client pour une configuration hybride avec votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="592ff-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="592ff-109">Un déploiement local unique (infrastructure) de Skype entreprise Server ou de Lync Server déployé dans une topologie prise en charge.</span><span class="sxs-lookup"><span data-stu-id="592ff-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="592ff-110">Voir la configuration requise pour la topologie.</span><span class="sxs-lookup"><span data-stu-id="592ff-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="592ff-111">Pour plus d’informations sur la configuration de votre déploiement Lync Server 2013 ou Lync Server 2010 pour une application hybride, voir [configuration de déploiements hybrides Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="592ff-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="592ff-112">Outils d’administration de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="592ff-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="592ff-113">Si vous utilisez Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser les outils d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="592ff-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="592ff-114">Pour prendre en charge l’authentification unique avec Office 365 de façon à ce que les utilisateurs puissent utiliser les mêmes informations d’identification pour se connecter à Office en local, vous pouvez utiliser les fonctionnalités de synchronisation de mot de passe d’Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="592ff-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="592ff-115">Vous pouvez également utiliser AD FS (Active Directory Federation Services) avec l’authentification unique pour Office 365.</span><span class="sxs-lookup"><span data-stu-id="592ff-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="592ff-116">Pour plus d’informations, consultez [intégration de vos identités locales avec Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="592ff-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="592ff-117">Une solution unique de synchronisation d’annuaires pour assurer la synchronisation de vos objets Active Directory locaux et en ligne.</span><span class="sxs-lookup"><span data-stu-id="592ff-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="592ff-118">Pour plus d’informations sur la synchronisation d’annuaires, voir [Outils d’intégration d’annuaire](http://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="592ff-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="592ff-119">Prise en charge du client Lync</span><span class="sxs-lookup"><span data-stu-id="592ff-119">Lync Client Support</span></span>

<span data-ttu-id="592ff-120">Il existe certaines différences entre les fonctionnalités prises en charge dans les clients Lync, ainsi que les fonctionnalités disponibles dans les environnements locaux et en ligne.</span><span class="sxs-lookup"><span data-stu-id="592ff-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="592ff-121">Avant de décider de l’endroit où vous souhaitez accéder aux utilisateurs de votre organisation, vous pouvez afficher la prise en charge du client pour les différentes configurations de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="592ff-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="592ff-122">Les clients suivants sont pris en charge dans Skype entreprise Online dans un déploiement hybride Lync:</span><span class="sxs-lookup"><span data-stu-id="592ff-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="592ff-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="592ff-123">Lync 2010</span></span>

  - <span data-ttu-id="592ff-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="592ff-124">Lync 2013</span></span>

  - <span data-ttu-id="592ff-125">application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="592ff-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="592ff-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="592ff-126">Lync Web App</span></span>

  - <span data-ttu-id="592ff-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="592ff-127">Lync Mobile</span></span>

  - <span data-ttu-id="592ff-128">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="592ff-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="592ff-129">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="592ff-129">Lync Room System</span></span>

  - <span data-ttu-id="592ff-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="592ff-130">Lync Basic 2013</span></span>

<span data-ttu-id="592ff-131">Pour plus d’informations sur la prise en charge des clients, voir les rubriques suivantes:</span><span class="sxs-lookup"><span data-stu-id="592ff-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="592ff-132">Clients pour Lync Online</span><span class="sxs-lookup"><span data-stu-id="592ff-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="592ff-133">Tableau de comparaison des clients pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="592ff-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="592ff-134">Tableau de comparaison des clients mobiles pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="592ff-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="592ff-135">Conditions requises pour la topologie</span><span class="sxs-lookup"><span data-stu-id="592ff-135">Topology Requirements</span></span>

<span data-ttu-id="592ff-136">Pour configurer votre déploiement pour une connexion hybride avec Skype entreprise Online, vous devez disposer de l’une des topologies prises en charge suivantes:</span><span class="sxs-lookup"><span data-stu-id="592ff-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="592ff-137">Un déploiement 2015 de Skype entreprise Server avec tous les serveurs exécutant Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="592ff-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="592ff-138">Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="592ff-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="592ff-139">Un déploiement Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les mises à jour les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="592ff-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="592ff-140">Le serveur de périphérie de Fédération et le serveur de tronçon suivant du serveur Edge de Fédération doivent exécuter Lync Server 2010 avec les mises à jour cumulatives les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="592ff-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="592ff-141">Les outils d’administration de Skype entreprise Server 2015 ou Lync Server 2013 doivent être installés sur au moins un serveur ou une station de travail de gestion.</span><span class="sxs-lookup"><span data-stu-id="592ff-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="592ff-142">Un déploiement Lync Server 2013 et Skype entreprise Server 2015 mixte avec les rôles serveur suivants dans au moins un site exécutant Skype entreprise Server 2015:</span><span class="sxs-lookup"><span data-stu-id="592ff-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="592ff-143">Au moins un pool d'entreprise ou serveur Standard Edition </span><span class="sxs-lookup"><span data-stu-id="592ff-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="592ff-144">Pool directeur associé à la fédération SIP, le cas échéant</span><span class="sxs-lookup"><span data-stu-id="592ff-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="592ff-145">Pool Edge associé à la fédération SIP</span><span class="sxs-lookup"><span data-stu-id="592ff-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="592ff-146">Un déploiement Lync Server 2010 et Skype entreprise Server 2015 mixte avec les rôles de serveurs suivants dans au moins un site exécutant Skype entreprise Server 2015:</span><span class="sxs-lookup"><span data-stu-id="592ff-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="592ff-147">Au moins un pool d'entreprise ou serveur Standard Edition </span><span class="sxs-lookup"><span data-stu-id="592ff-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="592ff-148">Pool directeur associé à la fédération SIP, le cas échéant</span><span class="sxs-lookup"><span data-stu-id="592ff-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="592ff-149">Pool Edge associé à la fédération SIP pour le site</span><span class="sxs-lookup"><span data-stu-id="592ff-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="592ff-150">Un déploiement Lync Server 2010 et Lync Server 2013 mixte avec les rôles serveur suivants dans au moins un site exécutant Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="592ff-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="592ff-151">Au moins un pool d'entreprise ou serveur Standard Edition dans le site</span><span class="sxs-lookup"><span data-stu-id="592ff-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="592ff-152">Pool directeur associé à la fédération SIP, si elle existe dans le site</span><span class="sxs-lookup"><span data-stu-id="592ff-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="592ff-153">Pool Edge associé à la fédération SIP pour le site</span><span class="sxs-lookup"><span data-stu-id="592ff-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="592ff-154">La gestion des utilisateurs, y compris les déplacements entre les utilisateurs locaux et UNRESOLVED_TOKEN_VAL (skypeforbusiness) en ligne, doit être effectuée à l’aide de la version installée la plus récente des outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="592ff-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="592ff-155">Les outils d’administration doivent être installés sur un serveur distinct qui dispose d’un accès de connexion au déploiement local existant et à Internet.</span><span class="sxs-lookup"><span data-stu-id="592ff-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="592ff-156">Pour déplacer des utilisateurs de votre déploiement local vers UNRESOLVED_TOKEN_VAL (skype16_online), l’applet de <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">passe Move-Csuser</A> doit être exécutée à partir des outils d’administration connectés à votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="592ff-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="592ff-157">Pour plus d’informations sur les topologies prises en charge, voir [topologies prises en charge dans Lync server 2013](lync-server-2013-supported-topologies.md)et [topologies de référence de Lync Server 2013 pour les déploiements hybrides d’entreprise](http://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="592ff-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="592ff-158">Pour plus d’informations sur les déploiements hybrides et la connexion de PowerShell à Lync Online, voir [Lync Online: Lync PowerShell et résolution des problèmes hybrides](http://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="592ff-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="592ff-159">Configuration requise pour les listes de Fédération autorisées/bloquées</span><span class="sxs-lookup"><span data-stu-id="592ff-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="592ff-p108">La liste des domaines autorisés comprend les domaines pour lesquels un nom de domaine complet Edge partenaire est configuré (parfois appelé *serveur partenaire autorisé* ou *partenaire de fédération direct*). Vous devez connaitre la différence entre la fédération ouverte et la fédération fermée, appelée *découverte de partenaire* et *liste de domaines partenaires autorisés*, dans les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="592ff-p108">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured. These are sometimes referred to as *allowed partner servers* or *direct federation partners*. You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="592ff-163">La configuration ci-dessous est requise pour configurer un déploiement hybride :</span><span class="sxs-lookup"><span data-stu-id="592ff-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="592ff-p109">La correspondance de domaine doit être identique pour votre déploiement local et votre client Office 365. Si la découverte de partenaire est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n'est pas activée, alors la fédération fermée doit être configurée pour votre client en ligne.</span><span class="sxs-lookup"><span data-stu-id="592ff-p109">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="592ff-167">La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.</span><span class="sxs-lookup"><span data-stu-id="592ff-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="592ff-168">La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.</span><span class="sxs-lookup"><span data-stu-id="592ff-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="592ff-169">La Fédération doit être activée pour les communications externes pour le client en ligne, qui est configuré à l’aide du panneau de configuration Lync Online.</span><span class="sxs-lookup"><span data-stu-id="592ff-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="592ff-170">Paramètres DNS</span><span class="sxs-lookup"><span data-stu-id="592ff-170">DNS Settings</span></span>

<span data-ttu-id="592ff-171">Lors de la création d’enregistrements DNS pour les déploiements hybrides, tous les enregistrements DNS externes Lync doivent pointer vers l’infrastructure locale.</span><span class="sxs-lookup"><span data-stu-id="592ff-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="592ff-172">Pour plus d’informations sur les enregistrements DNS requis, voir [Configuration requise pour le système de noms de domaine (DNS) pour Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="592ff-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="592ff-173">En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau ci-dessous fonctionne dans votre déploiement local :</span><span class="sxs-lookup"><span data-stu-id="592ff-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="592ff-174">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="592ff-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="592ff-175">Résolvable par</span><span class="sxs-lookup"><span data-stu-id="592ff-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="592ff-176">Enregistrement DNS requis</span><span class="sxs-lookup"><span data-stu-id="592ff-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="592ff-177">Enregistrement SRV DNS pour _sipfederationtls. _ TCP. &lt;sipdomain.com&gt; pour tous les domaines SIP pris en charge résolus vers les adresses IP externes d’Access Edge</span><span class="sxs-lookup"><span data-stu-id="592ff-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="592ff-178">Serveur(s) Edge</span><span class="sxs-lookup"><span data-stu-id="592ff-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="592ff-p111">Permettre la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où acheminer le trafic fédéré pour le domaine SIP qui est à la fois en local et en ligne.</span><span class="sxs-lookup"><span data-stu-id="592ff-p111">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="592ff-181">Enregistrement(s) DNS A pour le FQDN du service de conférence web Edge, par exemple webcon.contoso.com se résolvant en adresse(s) IP externe(s) Edge de conférence web</span><span class="sxs-lookup"><span data-stu-id="592ff-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="592ff-182">Ordinateurs des utilisateurs connectés au réseau d'entreprise interne</span><span class="sxs-lookup"><span data-stu-id="592ff-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="592ff-p112">Permettre aux utilisateurs de présenter ou d'afficher le contenu de réunions hébergées localement. Ce contenu peut inclure des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées. </span><span class="sxs-lookup"><span data-stu-id="592ff-p112">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="592ff-185">En fonction de la configuration DNS de votre organisation, vous devrez peut-être ajouter ces enregistrements dans la zone DNS hébergée en interne pour le(s) domaine(s) SIP correspondant(s) afin de fournir à ces enregistrements une résolution DNS interne.</span><span class="sxs-lookup"><span data-stu-id="592ff-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="592ff-186">Considérations en matière de pare-feu</span><span class="sxs-lookup"><span data-stu-id="592ff-186">Firewall Considerations</span></span>

<span data-ttu-id="592ff-p113">Les ordinateurs du réseau doivent être en mesure d'effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="592ff-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="592ff-189">En fonction de l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer les périphériques de pare-feu de votre réseau pour accepter les connexions basées sur les noms de \*domaine génériques (par exemple, tout le trafic de. Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="592ff-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="592ff-190">Si les pare-feu de votre organisation ne prennent pas en charge les configurations de nom génériques, vous devrez déterminer manuellement les plages d'adresses IP que vous voulez autoriser et les ports.</span><span class="sxs-lookup"><span data-stu-id="592ff-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="592ff-191">Reportez-vous à la rubrique d’aide [URL et plages d’adresses IP Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="592ff-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="592ff-192">Configuration requise pour les ports et les protocoles</span><span class="sxs-lookup"><span data-stu-id="592ff-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="592ff-193">En plus de la configuration requise pour les ports pour les communications internes de Lync Server 2013, vous devez également configurer les ports suivants.</span><span class="sxs-lookup"><span data-stu-id="592ff-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="592ff-194">Protocole/port</span><span class="sxs-lookup"><span data-stu-id="592ff-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="592ff-195">Applications</span><span class="sxs-lookup"><span data-stu-id="592ff-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="592ff-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="592ff-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="592ff-197">Ouvrir entrant</span><span class="sxs-lookup"><span data-stu-id="592ff-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="592ff-198">Services ADFS (Active Directory Federation Services)</span><span class="sxs-lookup"><span data-stu-id="592ff-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="592ff-199">Pour plus d’informations, voir <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Présentation des services de rôle AD FS</a>.</span><span class="sxs-lookup"><span data-stu-id="592ff-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="592ff-200">Services ADFS (Active Directory Federation Services) (rôle serveur proxy)</span><span class="sxs-lookup"><span data-stu-id="592ff-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="592ff-201">Portail Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="592ff-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="592ff-202">Mon portail d’entreprise</span><span class="sxs-lookup"><span data-stu-id="592ff-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="592ff-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="592ff-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="592ff-204">Client Lync (communications vers Lync Online à partir d’un serveur Lync local)</span><span class="sxs-lookup"><span data-stu-id="592ff-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="592ff-205">TCP 80 et 443</span><span class="sxs-lookup"><span data-stu-id="592ff-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="592ff-206">Ouvrir entrant</span><span class="sxs-lookup"><span data-stu-id="592ff-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="592ff-207">Outil de synchronisation d’annuaires de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="592ff-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="592ff-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="592ff-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="592ff-209">Ouvrir entrant/sortant sur le serveur de périphérie</span><span class="sxs-lookup"><span data-stu-id="592ff-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="592ff-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="592ff-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="592ff-211">Ouvrir entrant/sortant pour les sessions de partage de données</span><span class="sxs-lookup"><span data-stu-id="592ff-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="592ff-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="592ff-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="592ff-213">Ouvrir entrant/sortant pour les sessions audio, vidéo et de partage d’application</span><span class="sxs-lookup"><span data-stu-id="592ff-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="592ff-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="592ff-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="592ff-215">Ouvrir entrant/sortant pour les sessions audio et vidéo</span><span class="sxs-lookup"><span data-stu-id="592ff-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="592ff-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="592ff-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="592ff-217">Ouvrir sortant pour les sessions audio et vidéo</span><span class="sxs-lookup"><span data-stu-id="592ff-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="592ff-218">Comptes et données utilisateur</span><span class="sxs-lookup"><span data-stu-id="592ff-218">User Accounts and Data</span></span>

<span data-ttu-id="592ff-219">Dans le cas d’un déploiement hybride Lync Server 2013, tous les utilisateurs que vous souhaitez utiliser dans Lync Online doivent d’abord être créés dans le déploiement local, de sorte que le compte d’utilisateur est créé dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="592ff-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="592ff-220">Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise Online, qui va déplacer la liste de contacts de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="592ff-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="592ff-221">Lorsque vous synchronisez des comptes d’utilisateurs entre vos déploiements Lync local et Lync Online avec AD FS et DirSync, vous devez synchroniser les comptes d’annonces de tous les utilisateurs Lync de votre organisation entre votre déploiement local et Lync en ligne, même si les utilisateurs ne sont pas déplacés vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="592ff-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="592ff-222">Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="592ff-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="592ff-223">Si l’utilisateur est créé à l’aide du portail en ligne pour Office 365, le compte d’utilisateur n’est pas synchronisé avec Active Directory local et l’utilisateur n’existe pas dans l’annuaire Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="592ff-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="592ff-224">Si vous avez déjà créé des utilisateurs dans Lync Online et que vous souhaitez configurer une connexion hybride avec un serveur Lync local, voir <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">déplacement des utilisateurs de Lync Online vers Lync local dans Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="592ff-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="592ff-225">Lors de la planification d'un déploiement hybride, prenez en compte les aspects suivants liés aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="592ff-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="592ff-226">\*\*\*\* Le nombre maximal de contacts pour les utilisateurs de Lync Online 250 est fixé aux utilisateurs   </span><span class="sxs-lookup"><span data-stu-id="592ff-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="592ff-227">Au-delà de ce chiffre, les contacts seront supprimés de la liste des contacts de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="592ff-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="592ff-228">**Messagerie instantanée et présence**   les listes de contacts, groupes et listes de contrôle d’accès des utilisateurs sont migrés avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="592ff-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="592ff-229">**Les données de conférence, le contenu de la réunion et les réunions**   planifiées, ce contenu n’est pas migré avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="592ff-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="592ff-230">Les utilisateurs doivent replanifier les réunions une fois leur compte migré sur Lync Online.</span><span class="sxs-lookup"><span data-stu-id="592ff-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="592ff-231">Fonctionnalités et stratégies utilisateur</span><span class="sxs-lookup"><span data-stu-id="592ff-231">User Policies and Features</span></span>

  - <span data-ttu-id="592ff-232">Dans un environnement hybride Lync Server 2013, les utilisateurs peuvent être activés pour la messagerie instantanée, la voix et les réunions localement ou en ligne, mais pas les deux simultanément.</span><span class="sxs-lookup"><span data-stu-id="592ff-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="592ff-233">**Client Lync certains**     utilisateurs peuvent nécessiter une nouvelle version du client après leur déplacement vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="592ff-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="592ff-234">Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un pool Lync Server 2013 avant la migration vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="592ff-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="592ff-235">Pour plus d’informations sur la prise en charge des clients, voir [clients pour Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) et [clients et configurations de port réseau prises en charge](http://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="592ff-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="592ff-236">**Les stratégies locales et la configuration (non-utilisateur)**   en ligne et en local nécessitent une configuration distincte.</span><span class="sxs-lookup"><span data-stu-id="592ff-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="592ff-237">Vous ne pouvez pas définir des stratégies globales qui s'appliquent au deux.</span><span class="sxs-lookup"><span data-stu-id="592ff-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

