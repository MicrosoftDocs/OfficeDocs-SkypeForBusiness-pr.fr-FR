---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Protocoles de routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569202"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="e6905-103">Routage direct - Définitions et normes RFC</span><span class="sxs-lookup"><span data-stu-id="e6905-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="e6905-104">Cet article décrit comment le Téléphone Microsoft système direct implémente les protocoles standard RFC.</span><span class="sxs-lookup"><span data-stu-id="e6905-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="e6905-105">Cet article s’adresse aux administrateurs vocaux qui sont responsables de la configuration de la connexion entre le contrôleur des frontières de session (SBC) sur place et le service proxy du Protocole d’initiation de session (SIP).</span><span class="sxs-lookup"><span data-stu-id="e6905-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="e6905-106">Le client SBC interface avec les composants suivants dans le Microsoft Teams backend:</span><span class="sxs-lookup"><span data-stu-id="e6905-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="e6905-107">**Le proxy SIP** pour la signalisation.</span><span class="sxs-lookup"><span data-stu-id="e6905-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="e6905-108">Il s’agit de la composante internet de Direct Routing qui gère les connexions SIP (TLS) entre les SBCs et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="e6905-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="e6905-109">**Les processeurs multimédias** pour les médias.</span><span class="sxs-lookup"><span data-stu-id="e6905-109">**The media processors** for media.</span></span> <span data-ttu-id="e6905-110">Il s’agit de la composante internet de Direct Routing qui gère le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="e6905-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="e6905-111">Ce composant utilise les protocoles SRTP et SRTCP.</span><span class="sxs-lookup"><span data-stu-id="e6905-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="e6905-112">Pour plus d’informations sur le routage direct, [Système téléphonique le routage direct](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="e6905-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="e6905-113">Pour plus d’informations sur la façon dont Direct Routing implémente le protocole SIP, [voir Itinéraire direct - Protocole SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="e6905-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="e6905-114">Normes RFC</span><span class="sxs-lookup"><span data-stu-id="e6905-114">RFC standards</span></span>

<span data-ttu-id="e6905-115">Le routage direct est conforme aux normes RFC.</span><span class="sxs-lookup"><span data-stu-id="e6905-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="e6905-116">Le SBC connecté au routage direct doit également se conformer aux CRF suivants (ou à leurs successeurs).</span><span class="sxs-lookup"><span data-stu-id="e6905-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="e6905-117">Normes applicables aux appareils qui supporte le mode de contournement non médiatique</span><span class="sxs-lookup"><span data-stu-id="e6905-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="e6905-118">Les normes suivantes s’appliquent aux appareils qui ne supporte que le mode de contournement non médiatique :</span><span class="sxs-lookup"><span data-stu-id="e6905-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="e6905-119">[RFC 3261 SIP : Protocole d’initiation](https://tools.ietf.org/html/rfc3261)de session</span><span class="sxs-lookup"><span data-stu-id="e6905-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="e6905-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="e6905-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="e6905-121">Extension privée du protocole d’initiation à la session pour l’identité affirmée au sein des réseaux de confiance -- Sections sur le traitement de l’en-tête P-Asserted-Identity.</span><span class="sxs-lookup"><span data-stu-id="e6905-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="e6905-122">Le routage direct envoie p-asserted-identity avec des en-têtes privacy ID.</span><span class="sxs-lookup"><span data-stu-id="e6905-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="e6905-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Une extension du Protocole d’initiation à la session (SIP) pour les informations historiques requises.</span><span class="sxs-lookup"><span data-stu-id="e6905-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="e6905-124">Voir aussi : Routage de la description du protocole SIP pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="e6905-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="e6905-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Le Protocole d’initiation à la session Referred-By mécanisme</span><span class="sxs-lookup"><span data-stu-id="e6905-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="e6905-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Le Protocole d’initiation à la session (SIP) « remplace » l’en-tête</span><span class="sxs-lookup"><span data-stu-id="e6905-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="e6905-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Protocole d’initiation de session (SIP) Utilisation du modèle offre/réponse.</span><span class="sxs-lookup"><span data-stu-id="e6905-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="e6905-128">Voir la section « Déviations par rapport au RFC ».</span><span class="sxs-lookup"><span data-stu-id="e6905-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="e6905-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) et [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="e6905-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="e6905-130">Protégez le trafic RTP à l’aide de SRTP.</span><span class="sxs-lookup"><span data-stu-id="e6905-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="e6905-131">Le SBC doit être en mesure d’établir des clés à l’aide de SDES.</span><span class="sxs-lookup"><span data-stu-id="e6905-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="e6905-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Protocole de description de session (SDP) Offre/Clarifications de réponse pour le multiplexage RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="e6905-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="e6905-133">Normes applicables aux appareils qui supporte le mode de contournement des médias</span><span class="sxs-lookup"><span data-stu-id="e6905-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="e6905-134">En plus des normes énumérées comme applicables au mode non-bypass, les normes suivantes sont utilisées pour le mode de contournement des médias :</span><span class="sxs-lookup"><span data-stu-id="e6905-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="e6905-135">[RFC 5245 Interactive Connectivity Establishment (ICE) pour le contournement des médias](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="e6905-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="e6905-136">Le SBC doit prendre en charge les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e6905-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="e6905-137">ICE Lite - les clients Teams clients sont des clients ICE complets</span><span class="sxs-lookup"><span data-stu-id="e6905-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="e6905-138">[ICE Redémarre](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="e6905-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="e6905-139">En savoir plus sur ICE redémarre l’utilisation de cas et d’exemples dans ICE Restart: Media bypass call transféré à un point final qui ne prend pas en charge le contournement des médias</span><span class="sxs-lookup"><span data-stu-id="e6905-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="e6905-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfert](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="e6905-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="e6905-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)voir les sections 3.1, Forking, et 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="e6905-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="e6905-142">RFC 5389 Session Traversal Utilities pour NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="e6905-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="e6905-143">RFC 5766 Traversal Using Relays around NAT (TURN): Extensions relais à session Traversal Utilities for NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="e6905-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="e6905-144">Normes applicables pour appuyer la transmission d’informations de localisation aux fournisseurs de L’E911</span><span class="sxs-lookup"><span data-stu-id="e6905-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="e6905-145">RFC 6442, Transport de localisation pour le protocole d’initiation à la session</span><span class="sxs-lookup"><span data-stu-id="e6905-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="e6905-146">Déviations par rapport aux</span><span class="sxs-lookup"><span data-stu-id="e6905-146">Deviations from the RFC's</span></span>

<span data-ttu-id="e6905-147">Le tableau suivant énumère les sections du RFC(s) dans lesquelles la mise en œuvre par Microsoft du SIP ou de la pile multimédia s’écarte de la norme :</span><span class="sxs-lookup"><span data-stu-id="e6905-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="e6905-148">RFC et sections</span><span class="sxs-lookup"><span data-stu-id="e6905-148">RFC and sections</span></span> | <span data-ttu-id="e6905-149">Description</span><span class="sxs-lookup"><span data-stu-id="e6905-149">Description</span></span> | <span data-ttu-id="e6905-150">déviation</span><span class="sxs-lookup"><span data-stu-id="e6905-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="e6905-151">RFC 6337, section 5.3 Attente et curriculum vitae des médias</span><span class="sxs-lookup"><span data-stu-id="e6905-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="e6905-152">RFC permet d’utiliser « a=inactif », « a=sendonly », a=recvonly » pour mettre un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="e6905-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="e6905-153">Le proxy SIP ne prend en charge que « a=inactif » et ne comprend pas si le SBC envoie « a=sendonly » ou « a=recvonly ».</span><span class="sxs-lookup"><span data-stu-id="e6905-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="e6905-154">RFC 6337, section 5.4 « Comportement sur la réception du PDS avec c=0,0,0,0</span><span class="sxs-lookup"><span data-stu-id="e6905-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="e6905-155">[RFC3264 exige](https://tools.ietf.org/html/rfc3264) qu’un agent soit capable de recevoir SDP avec une adresse de connexion de 0.0.0.0, auquel cas cela signifie que ni RTP ni RTCP ne doivent être envoyés au pair.</span><span class="sxs-lookup"><span data-stu-id="e6905-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="e6905-156">Le proxy SIP ne prend pas en charge cette option.</span><span class="sxs-lookup"><span data-stu-id="e6905-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="e6905-157">Modes opérationnels</span><span class="sxs-lookup"><span data-stu-id="e6905-157">Operational modes</span></span>

<span data-ttu-id="e6905-158">Il existe deux modes opérationnels pour le routage direct :</span><span class="sxs-lookup"><span data-stu-id="e6905-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="e6905-159">**Sans contournement** médiatique dans lequel tout le trafic RTP circule entre Teams client, les processeurs multimédias et le SBC.</span><span class="sxs-lookup"><span data-stu-id="e6905-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="e6905-160">**Avec le contournement** des médias dans lequel tous les médias RTP circulent entre Teams points de terminaison et le SBC.</span><span class="sxs-lookup"><span data-stu-id="e6905-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="e6905-161">Notez que le trafic SIP circule toujours via le proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="e6905-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="e6905-162">Dtmf</span><span class="sxs-lookup"><span data-stu-id="e6905-162">DTMF</span></span>
<span data-ttu-id="e6905-163">Dans la bande DTMF n’est pas pris en charge par la pile de médias.</span><span class="sxs-lookup"><span data-stu-id="e6905-163">In-band DTMF is not supported by media stack.</span></span>
