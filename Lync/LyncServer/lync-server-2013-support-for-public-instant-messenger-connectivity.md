---
title: Prise en charge de Lync Server 2013 pour la connectivité de messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cd3c8cf89b9d5e1637db893b57e6b5955fbcee9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="084d7-102">Prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="084d7-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="084d7-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="084d7-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="084d7-104">Prise en charge de la connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="084d7-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="084d7-105">Cet article fournit des informations sur la prise en charge de la connectivité PIC (Public IM Connectivity).</span><span class="sxs-lookup"><span data-stu-id="084d7-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="084d7-106">La fonction PIC est une fonctionnalité de Microsoft Lync qui permet aux organisations de permettre à leurs utilisateurs Lync de se connecter aux utilisateurs de certains services de messagerie instantanée publique via leurs clients et identités Lync.</span><span class="sxs-lookup"><span data-stu-id="084d7-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="084d7-107">Les utilisateurs finaux peuvent être en mesure de rester en contact avec leurs clients, leurs partenaires et leurs fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="084d7-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="084d7-108">La prise en charge d’un client de communication en temps réel dans le cadre de la mise à jour des fonctionnalités de contrôle, de conformité et d’archivage de Lync a un avantage.</span><span class="sxs-lookup"><span data-stu-id="084d7-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="084d7-109">Lync-connectivité Skype, [publique disponible dans le 2013 de, s'](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)appuie sur l’ancien que Lync/Office Communications Server (OCS)/Live Communications Server (LCS) est d’abord établi avec la technologie pic de connexion à MSN/Windows Live, AOL et Yahoo.</span><span class="sxs-lookup"><span data-stu-id="084d7-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="084d7-110">Pour plus d’informations sur Lync-connectivité Skype, voir la [connectivité Lync-Skype](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="084d7-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="084d7-111">La Fédération avec Windows Live, AOL et Yahoo sont chacune sur une voie pour la fin de vie.</span><span class="sxs-lookup"><span data-stu-id="084d7-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="084d7-112">Cette page décrit l’état de chaque service.</span><span class="sxs-lookup"><span data-stu-id="084d7-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="084d7-113">Pour utiliser la photo, les clients ont été obligés d’activer le service pour chaque fournisseur de services de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="084d7-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="084d7-114">La configuration requise et les détails relatifs à cette action dépendent du fournisseur de services de messagerie instantanée et du programme de licence sous-jacent du client.</span><span class="sxs-lookup"><span data-stu-id="084d7-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="084d7-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="084d7-115">Windows Live Messenger</span></span>

<span data-ttu-id="084d7-116">Microsoft a mis en place Windows Live Messenger et Skype.</span><span class="sxs-lookup"><span data-stu-id="084d7-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="084d7-117">En avril 2013, les utilisateurs de Messenger ont migré vers Skype lors de la connexion.</span><span class="sxs-lookup"><span data-stu-id="084d7-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="084d7-118">Les clients Lync qui comptent sur une Fédération avec Messenger pourront toujours communiquer avec leurs contacts Messenger, même après la mise à jour de ces contacts sur Skype.</span><span class="sxs-lookup"><span data-stu-id="084d7-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="084d7-119">Il n’y a rien que les administrateurs Lync ou les utilisateurs finaux de Lync doivent effectuer pour maintenir la continuité du service et la gestion de cette fonctionnalité dans Lync reste la même que celle des communications avec Messenger.</span><span class="sxs-lookup"><span data-stu-id="084d7-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="084d7-120">Lorsque les utilisateurs de Messenger se connectent à Skype par le biais de leur compte Microsoft (c’est-à-dire, les mêmes informations d’identification utilisées pour Messenger) tous leurs contacts Messenger, y compris les contacts Lync fédérés, le suivent dans Skype.</span><span class="sxs-lookup"><span data-stu-id="084d7-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="084d7-121">Le partage de présence et la messagerie instantanée entre Skype et Lync pour ces contacts sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="084d7-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="084d7-122">Lync-connectivité Skype : l’ajout, le partage de présence, la messagerie instantanée et les appels audio entre Lync et les utilisateurs Skype sont également désormais disponibles pour tous les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="084d7-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="084d7-123">Yahoo !\!</span><span class="sxs-lookup"><span data-stu-id="084d7-123">Yahoo\!</span></span> <span data-ttu-id="084d7-124">et la messagerie instantanée sur AOL</span><span class="sxs-lookup"><span data-stu-id="084d7-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="084d7-125">Fédération avec Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="084d7-125">Federation with Yahoo\!</span></span> <span data-ttu-id="084d7-126">et AOL sont tous deux sur une voie pour la fin de vie des clients de Lync (et Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="084d7-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="084d7-127">La capacité de Microsoft à fournir chacun de ces services est subordonné à la prise en charge de Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="084d7-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="084d7-128">et AOL, et les accords sous-jacents de ces derniers sont en panne.</span><span class="sxs-lookup"><span data-stu-id="084d7-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="084d7-129">Pour Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="084d7-129">For both Yahoo\!</span></span> <span data-ttu-id="084d7-130">et AOL, le service va passer à la 2014 du 1er juin.</span><span class="sxs-lookup"><span data-stu-id="084d7-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="084d7-131">**Yahoo** -service va passer à la 2014 du 1er juin, et les clients continuent d’avoir besoin d’une licence pour la licence d’abonnement utilisateur de Microsoft Lync public Connectivity</span><span class="sxs-lookup"><span data-stu-id="084d7-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="084d7-132">À compter du 1er septembre, 2012, la USL., n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="084d7-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="084d7-133">Les clients disposant de licences achetées avant cette date seront en mesure de continuer à se fédérer avec Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="084d7-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="084d7-134">jusqu’à la date d’arrêt du service ou son expiration de la licence.</span><span class="sxs-lookup"><span data-stu-id="084d7-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="084d7-135">Lisez [l’annonce](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) publiée sur le blog de l’équipe Lync.</span><span class="sxs-lookup"><span data-stu-id="084d7-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="084d7-136">Les clients disposant de licences de PIC pour des accords qui dépassent le 30 juin, 2014 recevront un crédit au prorata du montant des paiements pour la période suivante : 30 juin 2014.</span><span class="sxs-lookup"><span data-stu-id="084d7-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="084d7-137">**AOL** : le 30 juin 2014, la connectivité de messagerie instantanée de Lync (« PIC ») ne sera plus disponible.</span><span class="sxs-lookup"><span data-stu-id="084d7-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="084d7-138">Pour limiter les perturbations du client lorsque le service se termine, nous avons abandonné le approvisionnement des domaines de clients supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="084d7-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="084d7-139">Jusqu’au 30 juin 2014, les clients n’ont rien à faire pour continuer à prendre en charge les communications fédérées avec AIM.</span><span class="sxs-lookup"><span data-stu-id="084d7-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="084d7-140">Au-delà de cette date (ou pour les clients souhaitant mettre en place des domaines supplémentaires), un service de substitution est disponible directement auprès d’AOL.</span><span class="sxs-lookup"><span data-stu-id="084d7-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="084d7-141">Pour plus d’informations sur le nouveau service d’AOL, voir [établissement de la Fédération directe avec AIM](http://aimenterprise.aol.com/pic.php)  (ouvre la nouvelle page sur AOL.com).</span><span class="sxs-lookup"><span data-stu-id="084d7-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="084d7-142">Résumé du fournisseur de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="084d7-142">Public IM Provider Summary</span></span>

<span data-ttu-id="084d7-143">Le tableau suivant récapitule les fournisseurs de services de messagerie instantanée publics, les fonctionnalités de Fédération avec Lync et les exigences en matière de licences.</span><span class="sxs-lookup"><span data-stu-id="084d7-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="084d7-144">Fournisseur de services de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="084d7-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="084d7-145">Fonctionnalités fédérées</span><span class="sxs-lookup"><span data-stu-id="084d7-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="084d7-146">Conditions de licence</span><span class="sxs-lookup"><span data-stu-id="084d7-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="084d7-147">Skype</span><span class="sxs-lookup"><span data-stu-id="084d7-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="084d7-148">Messagerie instantanée, présence, audio</span><span class="sxs-lookup"><span data-stu-id="084d7-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="084d7-149">Licences d’accès client Lync Server, Lync Online (plan 1/2/3)</span><span class="sxs-lookup"><span data-stu-id="084d7-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="084d7-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="084d7-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="084d7-151">Messagerie instantanée, présence, audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="084d7-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="084d7-152">Licences d’accès client de Lync Server (prises en charge dans la mesure où WLM est en marché)</span><span class="sxs-lookup"><span data-stu-id="084d7-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="084d7-153">AOL</span><span class="sxs-lookup"><span data-stu-id="084d7-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="084d7-154">Messagerie instantanée, présence</span><span class="sxs-lookup"><span data-stu-id="084d7-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="084d7-155">Licences d’accès client de Lync Server ; pris en charge par le 2014 juin pour les clients existants.</span><span class="sxs-lookup"><span data-stu-id="084d7-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="084d7-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="084d7-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="084d7-157">Messagerie instantanée, présence</span><span class="sxs-lookup"><span data-stu-id="084d7-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="084d7-158">Il est nécessaire de disposer d’une licence d’abonnement utilisateur Microsoft Lync public Connectivity supplémentaire (« PIC USL ») en plus des licences d’accès client Lync Server.</span><span class="sxs-lookup"><span data-stu-id="084d7-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="084d7-159">À compter du tarif de septembre 2012, la fonction USL de la photo n’est plus disponible à l’achat.</span><span class="sxs-lookup"><span data-stu-id="084d7-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="084d7-160">Les clients disposant de licences actives peuvent continuer à se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="084d7-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="084d7-161">Messenger tant que le service n’a pas été arrêté le 30 juin 2014.</span><span class="sxs-lookup"><span data-stu-id="084d7-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

