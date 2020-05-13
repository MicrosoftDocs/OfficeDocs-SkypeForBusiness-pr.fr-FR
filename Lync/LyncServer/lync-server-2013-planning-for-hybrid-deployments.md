---
title: 'Lync Server 2013 : planification des déploiements hybrides'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47e8bc57edbf3b6414820aba1613be8b44fc670e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="af986-102">Planification des déploiements hybrides Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af986-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af986-103">_**Dernière modification de la rubrique :** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="af986-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="af986-104">Vous devez tenir compte des exigences suivantes pour les utilisateurs et l’infrastructure réseau lors de la planification d’un déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="af986-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="af986-105">Conditions requises pour l’infrastructure</span><span class="sxs-lookup"><span data-stu-id="af986-105">Infrastructure Requirements</span></span>

<span data-ttu-id="af986-106">Les éléments suivants doivent être configurés dans votre environnement afin d’implémenter et de déployer un déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="af986-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="af986-107">Une organisation Microsoft 365 ou Office 365 avec Skype entreprise Online activé.</span><span class="sxs-lookup"><span data-stu-id="af986-107">A Microsoft 365 or Office 365 organization with Skype for Business Online enabled.</span></span> <span data-ttu-id="af986-108">Notez que vous ne pouvez utiliser qu’un seul client pour une configuration hybride avec votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="af986-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="af986-109">Un seul déploiement local (infrastructure) de Skype entreprise Server ou de Lync Server déployé dans une topologie prise en charge.</span><span class="sxs-lookup"><span data-stu-id="af986-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="af986-110">Consultez la rubrique Configuration requise pour la topologie.</span><span class="sxs-lookup"><span data-stu-id="af986-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="af986-111">Pour plus d’informations sur la configuration de votre déploiement Lync Server 2013 ou Lync Server 2010 en environnement hybride, consultez la rubrique [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="af986-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="af986-112">Outils d’administration de Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="af986-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="af986-113">Si vous utilisez Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser les outils d’administration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af986-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="af986-114">Pour prendre en charge l’authentification unique avec Microsoft 365 ou Office 365 de sorte que les utilisateurs puissent utiliser les mêmes informations d’identification de connexion pour se connecter à Office comme ils le font sur site, vous pouvez utiliser les fonctionnalités de synchronisation de mot de passe d’Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="af986-114">To support Single Sign-on with Microsoft 365 or Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="af986-115">Vous pouvez également utiliser les services ADFS (Active Directory Federation Services) pour l’authentification unique avec Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="af986-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Microsoft 365 or Office 365.</span></span>
    
    <span data-ttu-id="af986-116">Pour plus d'informations, voir [Intégration de vos identités locales avec Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="af986-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="af986-117">Une solution de synchronisation d’annuaire unique permettant de synchroniser vos objets Active Directory en local et en ligne.</span><span class="sxs-lookup"><span data-stu-id="af986-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="af986-118">Pour plus d’informations sur la synchronisation d’annuaires, consultez la rubrique [Outils d’intégration d’annuaire](https://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="af986-118">For details about Directory Synchronization, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="af986-119">Prise en charge des clients Lync</span><span class="sxs-lookup"><span data-stu-id="af986-119">Lync Client Support</span></span>

<span data-ttu-id="af986-120">Il existe certaines différences entre les fonctionnalités prises en charge par les clients Lync, ainsi que les fonctionnalités disponibles dans les environnements locaux et en ligne.</span><span class="sxs-lookup"><span data-stu-id="af986-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="af986-121">Avant de décider où vous voulez héberger les utilisateurs de votre organisation, vous pouvez afficher la prise en charge du client pour les différentes configurations de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af986-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="af986-122">Les clients suivants sont pris en charge avec Skype entreprise Online dans un déploiement Lync hybride :</span><span class="sxs-lookup"><span data-stu-id="af986-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="af986-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="af986-123">Lync 2010</span></span>

  - <span data-ttu-id="af986-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="af986-124">Lync 2013</span></span>

  - <span data-ttu-id="af986-125">Application Lync du Windows Store</span><span class="sxs-lookup"><span data-stu-id="af986-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="af986-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="af986-126">Lync Web App</span></span>

  - <span data-ttu-id="af986-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="af986-127">Lync Mobile</span></span>

  - <span data-ttu-id="af986-128">Lync pour Mac 2011</span><span class="sxs-lookup"><span data-stu-id="af986-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="af986-129">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="af986-129">Lync Room System</span></span>

  - <span data-ttu-id="af986-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="af986-130">Lync Basic 2013</span></span>

<span data-ttu-id="af986-131">Pour plus d’informations sur la prise en charge du client, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="af986-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="af986-132">Clients pour Lync Online</span><span class="sxs-lookup"><span data-stu-id="af986-132">Clients for Lync Online</span></span>](https://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="af986-133">Tableaux de comparaison des clients pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af986-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="af986-134">Tableaux de comparaison des clients mobiles pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af986-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="af986-135">Conditions requises pour la topologie</span><span class="sxs-lookup"><span data-stu-id="af986-135">Topology Requirements</span></span>

<span data-ttu-id="af986-136">Pour configurer votre déploiement hybride avec Skype entreprise Online, vous devez disposer de l’une des topologies prises en charge suivantes :</span><span class="sxs-lookup"><span data-stu-id="af986-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="af986-137">Un déploiement de Skype entreprise Server 2015 avec tous les serveurs exécutant Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="af986-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="af986-138">Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="af986-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="af986-139">Un déploiement de Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les mises à jour cumulatives les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="af986-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="af986-140">Le serveur Edge de Fédération et le serveur du tronçon suivant du serveur Edge de Fédération doivent exécuter Lync Server 2010 avec les mises à jour cumulatives les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="af986-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="af986-141">Les outils d’administration de Skype entreprise Server 2015 ou Lync Server 2013 doivent être installés sur au moins un serveur ou une station de gestion.</span><span class="sxs-lookup"><span data-stu-id="af986-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="af986-142">Un déploiement mixte de Lync Server 2013 et de Skype entreprise Server 2015 avec les rôles serveur suivants dans au moins un site exécutant Skype entreprise Server 2015 :</span><span class="sxs-lookup"><span data-stu-id="af986-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="af986-143">Au moins un pool d’entreprise ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="af986-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="af986-144">Pool Directeur associé à la Fédération SIP, le cas échéant</span><span class="sxs-lookup"><span data-stu-id="af986-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="af986-145">Pool de serveurs Edge associé à la Fédération SIP</span><span class="sxs-lookup"><span data-stu-id="af986-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="af986-146">Un déploiement mixte de Lync Server 2010 et de Skype entreprise Server 2015 avec les rôles de serveurs suivants dans au moins un site exécutant Skype entreprise Server 2015 :</span><span class="sxs-lookup"><span data-stu-id="af986-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="af986-147">Au moins un pool d’entreprise ou un serveur Standard Edition</span><span class="sxs-lookup"><span data-stu-id="af986-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="af986-148">Pool Directeur associé à la Fédération SIP, le cas échéant</span><span class="sxs-lookup"><span data-stu-id="af986-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="af986-149">Pool de serveurs Edge associé à la Fédération SIP pour le site</span><span class="sxs-lookup"><span data-stu-id="af986-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="af986-150">Un déploiement mixte de Lync Server 2010 et de Lync Server 2013 avec les rôles serveur suivants dans au moins un site exécutant Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="af986-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="af986-151">Au moins un pool d’entreprise ou un serveur Standard Edition dans le site</span><span class="sxs-lookup"><span data-stu-id="af986-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="af986-152">Pool Directeur associé à la Fédération SIP, s’il existe dans le site</span><span class="sxs-lookup"><span data-stu-id="af986-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="af986-153">Pool de serveurs Edge associé à la Fédération SIP pour le site</span><span class="sxs-lookup"><span data-stu-id="af986-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af986-154">Toutes les opérations de gestion des utilisateurs, y compris les déplacements entre les utilisateurs locaux et les UNRESOLVED_TOKEN_VAL (skypeforbusiness) en ligne, doivent être réalisées à l’aide de la dernière version installée des outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="af986-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="af986-155">Les outils d’administration doivent être installés sur un serveur distinct qui dispose d’un accès au déploiement local existant et à Internet.</span><span class="sxs-lookup"><span data-stu-id="af986-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="af986-156">La cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-Csuser</A> pour déplacer des utilisateurs de votre déploiement local vers UNRESOLVED_TOKEN_VAL (skype16_online) doit être exécutée à partir des outils d’administration connectés à votre déploiement local.</span><span class="sxs-lookup"><span data-stu-id="af986-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="af986-157">Pour plus d’informations sur les topologies prises en charge, voir [topologies prises en charge dans Lync server 2013](lync-server-2013-supported-topologies.md)et [topologies de référence Lync Server 2013 pour les déploiements hybrides d’entreprise](https://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="af986-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="af986-158">Pour plus d’informations sur la résolution des problèmes liés aux déploiements hybrides et à la connexion de PowerShell à Lync Online, voir [Lync Online : Lync PowerShell et Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="af986-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="af986-159">Configuration requise pour les listes autorisées/bloquées de la Fédération</span><span class="sxs-lookup"><span data-stu-id="af986-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="af986-160">La liste des domaines autorisés inclut des domaines dont le nom de domaine complet (FQDN) du partenaire est configuré.</span><span class="sxs-lookup"><span data-stu-id="af986-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="af986-161">Ces derniers sont parfois appelés *serveurs partenaires autorisés* ou *partenaires de Fédération directe*.</span><span class="sxs-lookup"><span data-stu-id="af986-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="af986-162">Vous devez être familiarisé avec la différence entre la Fédération ouverte et la Fédération fermée, respectivement appelée liste de domaines de *découverte* et de *domaine partenaire autorisés*dans les déploiements locaux.</span><span class="sxs-lookup"><span data-stu-id="af986-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="af986-163">Les conditions requises suivantes doivent être remplies pour pouvoir configurer un déploiement hybride :</span><span class="sxs-lookup"><span data-stu-id="af986-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="af986-164">La correspondance de domaine doit être configurée de la même façon pour votre déploiement local et votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="af986-164">Domain matching must be configured the same for your on-premises deployment and your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="af986-165">Si la découverte des partenaires est activée sur le déploiement local, la Fédération ouverte doit être configurée pour votre client en ligne.</span><span class="sxs-lookup"><span data-stu-id="af986-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="af986-166">Si la découverte de partenaire n’est pas activée, alors la Fédération fermée doit être configurée pour votre client en ligne.</span><span class="sxs-lookup"><span data-stu-id="af986-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="af986-167">La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.</span><span class="sxs-lookup"><span data-stu-id="af986-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="af986-168">La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.</span><span class="sxs-lookup"><span data-stu-id="af986-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="af986-169">La Fédération doit être activée pour les communications externes pour le client en ligne, qui est configuré à l’aide du panneau de configuration Lync Online.</span><span class="sxs-lookup"><span data-stu-id="af986-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="af986-170">Paramètres DNS</span><span class="sxs-lookup"><span data-stu-id="af986-170">DNS Settings</span></span>

<span data-ttu-id="af986-171">Lors de la création d’enregistrements DNS pour les déploiements hybrides, tous les enregistrements DNS externes de Lync doivent pointer vers l’infrastructure locale.</span><span class="sxs-lookup"><span data-stu-id="af986-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="af986-172">Pour plus d’informations sur les enregistrements DNS requis, reportez-vous à la rubrique [Domain Name System (DNS) Requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af986-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="af986-173">En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement local :</span><span class="sxs-lookup"><span data-stu-id="af986-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af986-174">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="af986-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="af986-175">Résolu par</span><span class="sxs-lookup"><span data-stu-id="af986-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="af986-176">Enregistrement DNS requis</span><span class="sxs-lookup"><span data-stu-id="af986-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af986-177">Enregistrement DNS SRV pour _sipfederationtls. _tcp. &lt; sipdomain.com &gt; pour tous les domaines SIP pris en charge résolus pour accéder à l’adresse IP externe du serveur Edge (s)</span><span class="sxs-lookup"><span data-stu-id="af986-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="af986-178">Serveur (s) Edge</span><span class="sxs-lookup"><span data-stu-id="af986-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="af986-179">Activer la communication fédérée dans une configuration hybride.</span><span class="sxs-lookup"><span data-stu-id="af986-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="af986-180">Le serveur Edge doit indiquer où acheminer le trafic fédéré pour le domaine SIP qui est réparti entre local et en ligne.</span><span class="sxs-lookup"><span data-stu-id="af986-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af986-181">Enregistrements DNS A (s) pour le nom de domaine complet du service de conférence Web Edge, par exemple webcon.contoso.com résolution des adresses IP externes Edge de conférence Web</span><span class="sxs-lookup"><span data-stu-id="af986-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="af986-182">Ordinateurs des utilisateurs connectés au réseau d’entreprise interne</span><span class="sxs-lookup"><span data-stu-id="af986-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="af986-183">Permettre aux utilisateurs en ligne de présenter ou d’afficher le contenu des réunions hébergées sur site.</span><span class="sxs-lookup"><span data-stu-id="af986-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="af986-184">Le contenu inclut des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="af986-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af986-185">En fonction de la configuration de DNS dans votre organisation, il se peut que vous deviez ajouter ces enregistrements à la zone DNS hébergée interne pour les domaines SIP correspondants afin de fournir la résolution DNS interne à ces enregistrements.</span><span class="sxs-lookup"><span data-stu-id="af986-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="af986-186">Considérations relatives au pare-feu</span><span class="sxs-lookup"><span data-stu-id="af986-186">Firewall Considerations</span></span>

<span data-ttu-id="af986-187">Les ordinateurs de votre réseau doivent être en mesure d’effectuer des recherches DNS Internet standard.</span><span class="sxs-lookup"><span data-stu-id="af986-187">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="af986-188">Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau répond à cette exigence.</span><span class="sxs-lookup"><span data-stu-id="af986-188">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="af986-189">En fonction de l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour qu’ils acceptent les connexions basées sur des noms de domaine génériques (par exemple, tout le trafic provenant de \* . Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="af986-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="af986-190">Si les pare-feu de votre organisation ne prennent pas en charge les configurations de nom génériques, vous devrez déterminer manuellement les plages d’adresses IP que vous voulez autoriser et les ports spécifiés.</span><span class="sxs-lookup"><span data-stu-id="af986-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="af986-191">Reportez-vous à la rubrique d’aide [URL et plages d’adresses IP Office 365](https://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="af986-191">Refer to the Help topic [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="af986-192">Configuration requise pour les ports et les protocoles</span><span class="sxs-lookup"><span data-stu-id="af986-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="af986-193">En plus des ports requis pour la communication interne de Lync Server 2013, vous devez également configurer les ports suivants.</span><span class="sxs-lookup"><span data-stu-id="af986-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af986-194">Protocole/port</span><span class="sxs-lookup"><span data-stu-id="af986-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="af986-195">Applications</span><span class="sxs-lookup"><span data-stu-id="af986-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af986-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="af986-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="af986-197">Ouvrir entrant</span><span class="sxs-lookup"><span data-stu-id="af986-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="af986-198">Services ADFS (rôle de serveur de fédération)</span><span class="sxs-lookup"><span data-stu-id="af986-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="af986-199">Pour plus d’informations, consultez la rubrique <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role services</a>.</span><span class="sxs-lookup"><span data-stu-id="af986-199">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="af986-200">Services ADFS (rôle de serveur proxy)</span><span class="sxs-lookup"><span data-stu-id="af986-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="af986-201">Portail Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="af986-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="af986-202">Portail de mon entreprise</span><span class="sxs-lookup"><span data-stu-id="af986-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="af986-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="af986-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="af986-204">Client Lync (communication vers Lync Online à partir de Lync Server sur site)</span><span class="sxs-lookup"><span data-stu-id="af986-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af986-205">TCP 80 et 443</span><span class="sxs-lookup"><span data-stu-id="af986-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="af986-206">Ouvrir entrant</span><span class="sxs-lookup"><span data-stu-id="af986-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="af986-207">Outil de synchronisation d’annuaires de Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="af986-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af986-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="af986-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="af986-209">Ouvrir les ports entrants/sortants sur le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="af986-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af986-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="af986-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="af986-211">Ouvrir les sessions de partage de données entrantes/sortantes</span><span class="sxs-lookup"><span data-stu-id="af986-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af986-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="af986-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="af986-213">Ouverture des sessions audio, vidéo et de partage d’application</span><span class="sxs-lookup"><span data-stu-id="af986-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af986-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="af986-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="af986-215">Ouvrir le trafic entrant/sortant pour les sessions audio et vidéo</span><span class="sxs-lookup"><span data-stu-id="af986-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af986-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="af986-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="af986-217">Ouvrir des sessions audio et vidéo sortantes</span><span class="sxs-lookup"><span data-stu-id="af986-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="af986-218">Comptes d’utilisateurs et données</span><span class="sxs-lookup"><span data-stu-id="af986-218">User Accounts and Data</span></span>

<span data-ttu-id="af986-219">Dans un déploiement hybride Lync Server 2013, tout utilisateur que vous souhaitez héberger dans Lync Online doit d’abord être créé dans le déploiement local, afin que le compte d’utilisateur soit créé dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="af986-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="af986-220">Vous pouvez ensuite déplacer l’utilisateur vers Skype entreprise Online, ce qui déplace la liste des contacts de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="af986-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="af986-221">Lorsque vous synchronisez des comptes d’utilisateurs entre vos déploiements Lync Online et Lync Online avec AD FS et DirSync, vous devez synchroniser les comptes AD de tous les utilisateurs Lync de votre organisation entre vos déploiements Lync sur site et en ligne, même si les utilisateurs ne sont pas déplacés vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="af986-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="af986-222">Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et les utilisateurs en ligne de votre organisation peut ne pas fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="af986-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af986-223">Si l’utilisateur est créé à l’aide du portail en ligne pour le centre d’administration Microsoft 365, le compte d’utilisateur n’est pas synchronisé avec Active Directory local et l’utilisateur n’existe pas dans l’environnement Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="af986-223">If the user is created by using the online portal for Microsoft 365 admin center, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="af986-224">Si vous avez déjà créé des utilisateurs dans Lync Online et que vous souhaitez configurer un environnement hybride avec un serveur Lync Server local, consultez la rubrique <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="af986-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="af986-225">Vous devez également tenir compte des problèmes liés aux utilisateurs suivants lors de la planification d’un déploiement hybride.</span><span class="sxs-lookup"><span data-stu-id="af986-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="af986-226">Contacts de l' **utilisateur**     Le nombre limite de contacts pour les utilisateurs Lync Online est de 250.</span><span class="sxs-lookup"><span data-stu-id="af986-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="af986-227">Tous les contacts au-delà de ce numéro seront supprimés de la liste des contacts de l’utilisateur lors du déplacement du compte vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="af986-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="af986-228">**Messagerie instantanée et présence**     Les listes de contacts de l’utilisateur, les groupes et les listes de contrôle d’accès (ACL) sont migrés avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="af986-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="af986-229">**Données de conférence, contenu de réunion et réunions**     planifiées Ce contenu n’est pas migré avec le compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="af986-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="af986-230">Les utilisateurs doivent replanifier les réunions après la migration de leurs comptes vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="af986-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="af986-231">Stratégies et fonctionnalités utilisateur</span><span class="sxs-lookup"><span data-stu-id="af986-231">User Policies and Features</span></span>

  - <span data-ttu-id="af986-232">Dans un environnement hybride Lync Server 2013, les utilisateurs peuvent être activés pour la messagerie instantanée, la voix et les réunions en local ou en ligne, mais pas les deux en même temps.</span><span class="sxs-lookup"><span data-stu-id="af986-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="af986-233">**Client Lync**     Certains utilisateurs peuvent exiger une nouvelle version du client lorsqu’ils sont déplacés vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="af986-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="af986-234">Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un pool Lync Server 2013 avant la migration vers Lync Online.</span><span class="sxs-lookup"><span data-stu-id="af986-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="af986-235">Pour plus d’informations sur la prise en charge des clients, voir [clients pour Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) et [clients Lync pris en charge et les configurations des ports réseau](https://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="af986-235">For more information about client support, see [Clients for Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="af986-236">**Configuration et stratégies locales (non utilisateur)**     Les stratégies en ligne et locales nécessitent une configuration distincte.</span><span class="sxs-lookup"><span data-stu-id="af986-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="af986-237">Vous ne pouvez pas définir des stratégies globales qui s’appliquent aux deux.</span><span class="sxs-lookup"><span data-stu-id="af986-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
