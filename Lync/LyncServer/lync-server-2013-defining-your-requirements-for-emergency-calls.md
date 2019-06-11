---
title: 'Lync Server 2013 : Définition de la configuration requise pour les appels d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53543d815519dc440ba038999e5fc531173551f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="98e8f-102">Définition de la configuration requise pour les appels d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98e8f-103">_**Dernière modification de la rubrique:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="98e8f-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="98e8f-104">Avant de commencer un déploiement de Microsoft Lync Server 2013 E9-1-1, vous devez d’abord répondre aux questions détaillées des sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="98e8f-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="98e8f-105">La planification dont vous avez besoin dépend du type de solution E9-1-1 que vous choisissez de déployer : fournisseur de services E9-1-1 de jonction SIP ou numéro ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="98e8f-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="98e8f-106">Le tableau ci-dessous identifie les sections du document de planification à consulter pour chacune de ces solutions.</span><span class="sxs-lookup"><span data-stu-id="98e8f-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="98e8f-107">Étapes de planification par type de solution E9-1-1</span><span class="sxs-lookup"><span data-stu-id="98e8f-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98e8f-108">Fournisseur de services de jonction SIP</span><span class="sxs-lookup"><span data-stu-id="98e8f-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="98e8f-109">Passerelle ELIN</span><span class="sxs-lookup"><span data-stu-id="98e8f-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98e8f-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e8f-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e8f-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e8f-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gestion des emplacements pour les fournisseurs de services SIP Trunk dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e8f-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Définition de l’interface utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Définition de l’interface utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e8f-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP Trunk pour E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-121"><a href="lync-server-2013-including-the-security-desk.md">Inclure le centre de sécurité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e8f-122"><a href="lync-server-2013-including-the-security-desk.md">Inclure le centre de sécurité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-123"><a href="lync-server-2013-defining-the-location-policy.md">Définition de la stratégie d’emplacement pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e8f-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choix d’un fournisseur de services E9-1-1 pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="98e8f-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Attribution de l’étendue de la stratégie d’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98e8f-126"><a href="lync-server-2013-defining-the-location-policy.md">Définition de la stratégie d’emplacement pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98e8f-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Attribution de l’étendue de la stratégie d’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="98e8f-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="98e8f-128">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="98e8f-128">In This Section</span></span>

  - [<span data-ttu-id="98e8f-129">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="98e8f-130">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="98e8f-131">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="98e8f-132">Gestion des emplacements pour les fournisseurs de services SIP Trunk dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="98e8f-133">Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="98e8f-134">Définition de l’interface utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="98e8f-135">Designing the SIP Trunk pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="98e8f-136">Inclure le centre de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="98e8f-137">Choix d’un fournisseur de services E9-1-1 pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="98e8f-138">Définition de la stratégie d’emplacement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="98e8f-139">Attribution de l’étendue de la stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98e8f-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

