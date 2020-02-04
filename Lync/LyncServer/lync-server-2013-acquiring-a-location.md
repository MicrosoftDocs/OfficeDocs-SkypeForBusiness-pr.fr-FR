---
title: 'Lync Server 2013 : Acquisition d’un emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="bc4d1-102">Acquisition d’un emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc4d1-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc4d1-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="bc4d1-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="bc4d1-104">Dans un déploiement Lync Server 2013 E9-1-1, chaque client Lync connecté en interne ou Lync Phone Edition acquiert activement son emplacement.</span><span class="sxs-lookup"><span data-stu-id="bc4d1-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="bc4d1-105">Après l’inscription SIP, le client fournit toutes les informations de connectivité réseau qu’il connaît lui-même dans une demande d’emplacement du service d’information d’emplacement, qui est un service Web stocké par une base de données SQL Server répliquée.</span><span class="sxs-lookup"><span data-stu-id="bc4d1-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="bc4d1-106">Chacun d’eux dispose d’un service d’information d’emplacement qui utilise les informations réseau pour rechercher un emplacement correspondant dans ses enregistrements.</span><span class="sxs-lookup"><span data-stu-id="bc4d1-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="bc4d1-107">S’il existe une correspondance, le service d’informations d’emplacement renvoie un emplacement au client.</span><span class="sxs-lookup"><span data-stu-id="bc4d1-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="bc4d1-108">Dans le cas inverse, l’utilisateur peut être invité à entrer manuellement un emplacement (en fonction des paramètres de la stratégie d’emplacement).</span><span class="sxs-lookup"><span data-stu-id="bc4d1-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="bc4d1-109">Les données d’emplacement sont retransmises au client dans un format XML normalisé IETF (Internet Engineering Task Force) appelé PIDF-LO (Presence Information Data Format Location Object).</span><span class="sxs-lookup"><span data-stu-id="bc4d1-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="bc4d1-110">Le client Lync Server inclut les données PIDF-LO dans le cadre d’un appel d’urgence, et ces données sont utilisées par le prestataire de services E9-1-1 pour déterminer le PSAPI approprié et acheminer l’appel vers ce PSAPI avec le bon ESQK, ce qui permet au répartiteur PSAPI d’obtenir le emplacement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="bc4d1-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="bc4d1-111">Le diagramme suivant montre comment un client Lync Server acquiert un emplacement (à l’exception de la méthode d’emplacement basée sur l’adresse MAC du client tiers) :</span><span class="sxs-lookup"><span data-stu-id="bc4d1-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="bc4d1-112">![Diagramme : comment le client acquiert un emplacement](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Diagramme : comment le client acquiert un emplacement")</span><span class="sxs-lookup"><span data-stu-id="bc4d1-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="bc4d1-113">Pour qu’un client acquière un emplacement, les étapes suivantes doivent se produire :</span><span class="sxs-lookup"><span data-stu-id="bc4d1-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="bc4d1-114">L’administrateur remplit la base de données de service informations d’emplacement avec le Network Wiremap (tables qui mappent différents types d’adresses réseau aux emplacements de réponse d’urgence correspondants (ERLs)).</span><span class="sxs-lookup"><span data-stu-id="bc4d1-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="bc4d1-p102">Si vous utilisez un fournisseur de service E9-1-1 de jonction SIP, l’administrateur valide les parties d’adresse civile des ERL par rapport à la base de données MSAG (Master Street Address Guide) maintenue par le fournisseur de service E9-1-1. Si vous utilisez une passerelle ELIN, l’administrateur s’assure que l’opérateur RTC télécharge les ELIN dans la base de données ALI (Automatic Location Identification).</span><span class="sxs-lookup"><span data-stu-id="bc4d1-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="bc4d1-117">Lors de l’inscription ou en cas de modification d’un réseau, un client connecté en interne envoie une demande d’emplacement contenant les adresses réseau découvertes du client au service d’informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="bc4d1-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="bc4d1-118">Le service d’informations d’emplacement interroge ses enregistrements publiés pour un emplacement et, si une correspondance est trouvée, renvoie la propriété ERL au client en format PIDF-Low.</span><span class="sxs-lookup"><span data-stu-id="bc4d1-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

