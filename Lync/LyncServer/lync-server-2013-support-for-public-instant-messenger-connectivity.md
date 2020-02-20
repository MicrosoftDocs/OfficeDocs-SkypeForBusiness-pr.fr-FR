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
ms.openlocfilehash: 3c6f21e6a58b9130ab93f827f14aad4bd09cbb33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="d6b1b-102">Prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b1b-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6b1b-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="d6b1b-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="d6b1b-104">Prise en charge de la connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="d6b1b-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="d6b1b-105">Cet article fournit des informations sur la prise en charge de la connectivité PIC (Public IM Connectivity).</span><span class="sxs-lookup"><span data-stu-id="d6b1b-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="d6b1b-106">PIC est une fonctionnalité de Microsoft Lync qui permet aux organisations de permettre aux utilisateurs de communiquer avec des utilisateurs de certains services de messagerie instantanée (IM) publics via leurs clients et identités Lync.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="d6b1b-107">Les utilisateurs finaux peuvent se connecter aux clients, partenaires et fournisseurs en fonction de leurs termes.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="d6b1b-108">Il bénéficie de la prise en charge d’un seul client de communications en temps réel tout en conservant les fonctionnalités de contrôle, de conformité et d’archivage de Lync.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="d6b1b-109">Lync-Skype Connectivity, [accessible publiquement en mai 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), repose sur l’héritage que Lync/Office Communications Server (LCS) a créé en premier lieu avec la mise à niveau vers MSN/Windows Live, AOL et Yahoo.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-109">Lync-Skype connectivity, [publicly available in May 2013](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="d6b1b-110">Pour plus d’informations sur la connectivité Lync-Skype, reportez-vous à la rubrique [Lync-Skype Connectivity](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="d6b1b-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="d6b1b-111">La Fédération avec Windows Live, AOL et Yahoo se situent dans un chemin d’accès à la fin de vie.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="d6b1b-112">Cette page décrit l’état de chaque service.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="d6b1b-113">Pour utiliser PIC, les clients doivent activer le service pour chaque fournisseur de services de messagerie instantanée public.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="d6b1b-114">Les conditions requises et les détails relatifs à cette opération dépendent du fournisseur de services de messagerie instantanée et du programme de gestion des licences sous-jacent du client.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="d6b1b-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d6b1b-115">Windows Live Messenger</span></span>

<span data-ttu-id="d6b1b-116">Microsoft a mis en place Windows Live Messenger et Skype.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="d6b1b-117">En avril 2013, les utilisateurs de Messenger ont été migrés vers Skype lors de la connexion.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="d6b1b-118">Les clients Lync qui comptent sur la Fédération avec Messenger continueront à pouvoir communiquer avec leurs contacts Messenger, même après la mise à jour de ces contacts vers Skype.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="d6b1b-119">Il n’y a rien que les administrateurs Lync ou les utilisateurs finaux Lync doivent effectuer pour maintenir la continuité du service, et la gestion de cette fonctionnalité dans Lync reste identique à celle des communications avec Messenger.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="d6b1b-120">Lorsque les utilisateurs de Messenger se connectent à Skype à l’aide de leurs comptes Microsoft (c’est-à-dire, les mêmes informations d’identification utilisées pour Messenger), tous leurs contacts Messenger, y compris les contacts Lync fédérés, les suivent dans Skype.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="d6b1b-121">Le partage de présence et la messagerie instantanée entre Skype et Lync pour ces contacts sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="d6b1b-122">Lync-la connectivité Skype : l’ajout, le partage de présence, la messagerie instantanée et l’appel audio entre Lync et les utilisateurs Skype sont également disponibles pour tous les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="d6b1b-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d6b1b-123">Yahoo\!</span></span> <span data-ttu-id="d6b1b-124">et AOL Instant Messenger</span><span class="sxs-lookup"><span data-stu-id="d6b1b-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="d6b1b-125">Fédération avec Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d6b1b-125">Federation with Yahoo\!</span></span> <span data-ttu-id="d6b1b-126">en effet, AOL se trouve à la fois sur un chemin de fin de vie pour les clients de Lync (et Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="d6b1b-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="d6b1b-127">La capacité de Microsoft à fournir chacun de ces services a été subordonnée à la prise en charge de Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d6b1b-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="d6b1b-128">et AOL, et les accords sous-jacents de ceux-ci sont démontés.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="d6b1b-129">Pour Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d6b1b-129">For both Yahoo\!</span></span> <span data-ttu-id="d6b1b-130">et AOL, le service se poursuivra jusqu’au 2014 juin.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="d6b1b-131">**Yahoo** -service se poursuivra jusqu’au 2014 juin, et les clients continueront à utiliser la licence d’abonnement utilisateur Microsoft LYNC Public IM Connectivity (« PIC USL »).</span><span class="sxs-lookup"><span data-stu-id="d6b1b-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="d6b1b-132">Depuis le 1er septembre, le 2012, la couche USL, n’est plus disponible à l’achat pour les contrats de nouvelle ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="d6b1b-133">Les clients disposant de licences achetées avant cette date seront en mesure de continuer à fédérer avec Yahoo.\!</span><span class="sxs-lookup"><span data-stu-id="d6b1b-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="d6b1b-134">jusqu’à la date antérieure de l’arrêt du service ou de leur expiration de la licence.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="d6b1b-135">Lisez [l’annonce](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) sur le blog de l’équipe Lync.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-135"> Read [the announcement](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="d6b1b-136">Les clients disposant de licences PIC sur des accords qui dépassent le 30 juin 2014 recevront un crédit proportionnellement au montant des paiements couvrant le délai suivant : 30 juin 2014.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="d6b1b-137">**AOL** -le 30 juin 2014, le service de connectivité de messagerie instantanée de Lync (« PIC ») ne sera plus disponible.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="d6b1b-138">Afin de limiter le nombre d’interruptions client lorsque le service se termine, nous avons abandonné la mise en service des domaines de client supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="d6b1b-139">Jusqu’au 30 juin 2014, les clients n’ont rien besoin de faire quoi que ce soit pour continuer à prendre en charge les communications fédérées avec AIM.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="d6b1b-140">Au-delà de cette date (ou pour les clients qui souhaitent configurer des domaines supplémentaires en attendant), un service de remplacement est disponible directement auprès d’AOL.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="d6b1b-141">Pour plus d’informations sur le nouveau service d’AOL, consultez la rubrique établissement de la [Fédération directe avec AIM](http://aimenterprise.aol.com/pic.php)  (ouvre la nouvelle page sur AOL.com).</span><span class="sxs-lookup"><span data-stu-id="d6b1b-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="d6b1b-142">Résumé des fournisseurs de messagerie instantanée publics</span><span class="sxs-lookup"><span data-stu-id="d6b1b-142">Public IM Provider Summary</span></span>

<span data-ttu-id="d6b1b-143">Le tableau suivant fournit un résumé des fournisseurs de services de messagerie instantanée publics, des fonctionnalités de Fédération avec Lync et des exigences en matière de licences.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6b1b-144">Fournisseur de services de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="d6b1b-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="d6b1b-145">Fonctionnalités fédérées</span><span class="sxs-lookup"><span data-stu-id="d6b1b-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="d6b1b-146">Conditions de licence</span><span class="sxs-lookup"><span data-stu-id="d6b1b-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6b1b-147">Skype</span><span class="sxs-lookup"><span data-stu-id="d6b1b-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-148">Messagerie instantanée, présence, audio</span><span class="sxs-lookup"><span data-stu-id="d6b1b-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-149">Licences d’accès client Lync Server, Lync Online plan 1/2/3</span><span class="sxs-lookup"><span data-stu-id="d6b1b-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b1b-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="d6b1b-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-151">Messagerie instantanée, présence, audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="d6b1b-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-152">Licences d’accès au client Lync Server (prises en charge tant que WLM est sur le marché)</span><span class="sxs-lookup"><span data-stu-id="d6b1b-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6b1b-153">AOL</span><span class="sxs-lookup"><span data-stu-id="d6b1b-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-154">Messagerie instantanée, présence</span><span class="sxs-lookup"><span data-stu-id="d6b1b-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-155">Licences d’accès au client Lync Server ; pris en charge jusqu’en juin 2014 pour les clients existants.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6b1b-156">Payant</span><span class="sxs-lookup"><span data-stu-id="d6b1b-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-157">Messagerie instantanée, présence</span><span class="sxs-lookup"><span data-stu-id="d6b1b-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="d6b1b-158">Nécessite une licence d’abonnement utilisateur Microsoft Lync public Connectivity supplémentaire (« PIC USL ») en plus des licences d’accès au client Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="d6b1b-159">À partir de la liste de prix de septembre 2012, la fonction USL n’est plus disponible à l’achat.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="d6b1b-160">Les clients disposant de licences actives peuvent continuer à fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="d6b1b-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d6b1b-161">Messenger jusqu’à la date d’arrêt du service le 30 juin 2014.</span><span class="sxs-lookup"><span data-stu-id="d6b1b-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
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

