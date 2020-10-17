---
title: 'Lync Server 2013 : définition de la configuration requise pour les appels d’urgence'
description: 'Lync Server 2013 : définition de la configuration requise pour les appels d’urgence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d3c9908dcb4008a1442af86971e42eb4096a98b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545400"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="0d48a-103">Définition de la configuration requise pour les appels d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-103">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d48a-104">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="0d48a-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="0d48a-105">Avant de commencer un déploiement de Microsoft Lync Server 2013 E9-1-1, vous devez d’abord pouvoir répondre aux questions détaillées dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="0d48a-105">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="0d48a-106">La planification dont vous avez besoin dépend du type de solution E9-1-1 que vous choisissez de déployer : fournisseur de services E9-1-1 de jonction SIP ou numéro ELIN (Emergency Location Identification Number).</span><span class="sxs-lookup"><span data-stu-id="0d48a-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="0d48a-107">Le tableau suivant identifie les sections du document de planification que vous devez consulter pour chacune de ces solutions.</span><span class="sxs-lookup"><span data-stu-id="0d48a-107">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="0d48a-108">Étapes de planification par type de solution E9-1-1</span><span class="sxs-lookup"><span data-stu-id="0d48a-108">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d48a-109">Fournisseur de services de jonction SIP</span><span class="sxs-lookup"><span data-stu-id="0d48a-109">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="0d48a-110">Passerelle ELIN</span><span class="sxs-lookup"><span data-stu-id="0d48a-110">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d48a-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-112"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d48a-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-114"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d48a-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-116"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d48a-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Gestion des emplacements pour les fournisseurs de services de jonction SIP dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-117"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-118"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d48a-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-120"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d48a-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Conception de la jonction SIP pour E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-121"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-122"><a href="lync-server-2013-including-the-security-desk.md">Inclusion du service de sécurité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d48a-123"><a href="lync-server-2013-including-the-security-desk.md">Inclusion du service de sécurité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-123"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-124"><a href="lync-server-2013-defining-the-location-policy.md">Définition de la stratégie d’emplacement pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-124"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d48a-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choix d’un fournisseur de services E9-1-1 pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-125"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0d48a-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-126"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d48a-127"><a href="lync-server-2013-defining-the-location-policy.md">Définition de la stratégie d’emplacement pour Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-127"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d48a-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0d48a-128"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="0d48a-129">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0d48a-129">In This Section</span></span>

  - [<span data-ttu-id="0d48a-130">Définition de l’étendue du déploiement E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-130">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="0d48a-131">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-131">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="0d48a-132">Activation des utilisateurs pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-132">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="0d48a-133">Gestion des emplacements pour les fournisseurs de services de jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-133">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="0d48a-134">Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-134">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="0d48a-135">Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-135">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="0d48a-136">Conception de la jonction SIP pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-136">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="0d48a-137">Inclusion du service de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-137">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="0d48a-138">Choix d’un fournisseur de services E9-1-1 pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-138">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="0d48a-139">Définition de la stratégie d’emplacement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-139">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="0d48a-140">Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d48a-140">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

