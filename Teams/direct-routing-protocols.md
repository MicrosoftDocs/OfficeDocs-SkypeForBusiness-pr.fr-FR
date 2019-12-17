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
description: Protocoles de routage directe
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065624"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="f9509-103">Itinéraires directs-définitions et normes RFC</span><span class="sxs-lookup"><span data-stu-id="f9509-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="f9509-104">Cet article décrit comment le routage direct du système Microsoft Phone implémente les protocoles standard RFC.</span><span class="sxs-lookup"><span data-stu-id="f9509-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="f9509-105">Cet article est destiné aux administrateurs de voix qui sont responsables de la configuration de la connexion entre le contrôleur de bordure de session (SBC) local et le service proxy SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="f9509-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="f9509-106">Les interfaces clientes SBC avec les composants suivants du serveur principal Microsoft teams :</span><span class="sxs-lookup"><span data-stu-id="f9509-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="f9509-107">**Le proxy SIP pour la** signalisation.</span><span class="sxs-lookup"><span data-stu-id="f9509-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="f9509-108">Il s’agit du composant Internet du routage direct qui gère les connexions SIP (TLS) entre le routage SBCs et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="f9509-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="f9509-109">**Processeurs multimédias** pour médias.</span><span class="sxs-lookup"><span data-stu-id="f9509-109">**The media processors** for media.</span></span> <span data-ttu-id="f9509-110">Il s’agit du composant Internet du routage direct qui gère le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="f9509-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="f9509-111">Ce composant utilise les protocoles SRTP et SRTCP.</span><span class="sxs-lookup"><span data-stu-id="f9509-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="f9509-112">Pour plus d’informations sur le routage direct, voir [routage direct du système téléphonique](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="f9509-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="f9509-113">Pour plus d’informations sur l’implémentation du protocole SIP par le routage direct, voir [routage direct-protocole SIP](direct-routing-protocols-sip.md).</span><span class="sxs-lookup"><span data-stu-id="f9509-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="f9509-114">Normes RFC</span><span class="sxs-lookup"><span data-stu-id="f9509-114">RFC standards</span></span>

<span data-ttu-id="f9509-115">Le routage direct répond aux normes RFC.</span><span class="sxs-lookup"><span data-stu-id="f9509-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="f9509-116">Le SBC connecté au routage direct doit également respecter les RFC suivantes (ou leurs successeurs).</span><span class="sxs-lookup"><span data-stu-id="f9509-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="f9509-117">Normes applicables aux appareils qui prennent en charge le mode de contournement non multimédia</span><span class="sxs-lookup"><span data-stu-id="f9509-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="f9509-118">Les normes suivantes s’appliquent aux appareils qui prennent en charge uniquement le mode de contournement non multimédia :</span><span class="sxs-lookup"><span data-stu-id="f9509-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="f9509-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): protocole d’initiation de session</span><span class="sxs-lookup"><span data-stu-id="f9509-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="f9509-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="f9509-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="f9509-121">Extension privée du protocole d’initiation de session pour l’identité affirmée au sein de réseaux approuvés : sections sur la gestion de l’en-tête d’identité P-assertion.</span><span class="sxs-lookup"><span data-stu-id="f9509-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="f9509-122">Le routage direct envoie l’identité P-assertion avec les en-têtes d’ID de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="f9509-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="f9509-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Extension du protocole SIP (Session Initiation Protocol) pour les informations d’historique requises.</span><span class="sxs-lookup"><span data-stu-id="f9509-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="f9509-124">Voir aussi : description du protocole SIP de routage pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="f9509-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="f9509-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Mécanisme référencé par le protocole d’initiation de session</span><span class="sxs-lookup"><span data-stu-id="f9509-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="f9509-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) L’en-tête SIP (Session Initiation Protocol) "remplace"</span><span class="sxs-lookup"><span data-stu-id="f9509-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="f9509-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Utilisation SIP (Session Initiation Protocol) du modèle d’une proposition/réponse.</span><span class="sxs-lookup"><span data-stu-id="f9509-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="f9509-128">Voir la section « déviations de RFC ».</span><span class="sxs-lookup"><span data-stu-id="f9509-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="f9509-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711) et [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="f9509-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="f9509-130">Protégez le trafic RTP à l’aide de SRTP.</span><span class="sxs-lookup"><span data-stu-id="f9509-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="f9509-131">L’SBC doit être en mesure d’établir des clés avec SDES.</span><span class="sxs-lookup"><span data-stu-id="f9509-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="f9509-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Clarifications ou réponses du protocole SDP (session Description Protocol) pour multiplexage RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="f9509-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="f9509-133">Normes applicables aux appareils prenant en charge le mode de contournement multimédia</span><span class="sxs-lookup"><span data-stu-id="f9509-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="f9509-134">Outre les normes répertoriées comme applicables au mode non-contournement, les normes suivantes sont utilisées pour le mode de contournement multimédia :</span><span class="sxs-lookup"><span data-stu-id="f9509-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="f9509-135">[RFC 5245 interactive Connectivity Establishing (ICE) pour Bypass Media](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="f9509-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="f9509-136">L’SBC doit prendre en charge les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f9509-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="f9509-137">ICE Lite : les clients teams sont des clients de glace complète</span><span class="sxs-lookup"><span data-stu-id="f9509-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="f9509-138">Les [redémarrages de glace](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span><span class="sxs-lookup"><span data-stu-id="f9509-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="f9509-139">Pour en savoir plus sur les redémarrages de glace, utilisez le cas et les exemples dans le redémarrage</span><span class="sxs-lookup"><span data-stu-id="f9509-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="f9509-140">[Contrôle du protocole SIP rfc 5589 (Session Initiation Protocol)-transfert](https://tools.ietf.org/html/rfc5589).</span><span class="sxs-lookup"><span data-stu-id="f9509-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="f9509-141">[RFC 3960 premiers médias et la génération de tonalités de sonnerie dans le protocole SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3960), voir les sections 3,1, fork et 3,2, Generation de sonnerie</span><span class="sxs-lookup"><span data-stu-id="f9509-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="f9509-142">Utilitaires de traversée de session RFC 5389 pour NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="f9509-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="f9509-143">RFC 5766 traversée à l’aide de relais sur NAT (TURN) : les extensions de relais aux utilitaires de traversée de session pour tar (STUN)</span><span class="sxs-lookup"><span data-stu-id="f9509-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="f9509-144">Normes applicables pour la prise en charge du transport d’informations d’emplacement vers les fournisseurs de E911</span><span class="sxs-lookup"><span data-stu-id="f9509-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="f9509-145">RFC 6442, le transport d’emplacement du protocole d’initiation de session</span><span class="sxs-lookup"><span data-stu-id="f9509-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="f9509-146">Écarts par rapport aux RFC</span><span class="sxs-lookup"><span data-stu-id="f9509-146">Deviations from the RFC's</span></span>

<span data-ttu-id="f9509-147">Le tableau suivant répertorie les sections des RFC (s) dans lesquelles l’implémentation de la pile SIP ou multimédias de Microsoft s’écarte de la norme :</span><span class="sxs-lookup"><span data-stu-id="f9509-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="f9509-148">RFC et sections</span><span class="sxs-lookup"><span data-stu-id="f9509-148">RFC and sections</span></span> | <span data-ttu-id="f9509-149">Description</span><span class="sxs-lookup"><span data-stu-id="f9509-149">Description</span></span> | <span data-ttu-id="f9509-150">Écart</span><span class="sxs-lookup"><span data-stu-id="f9509-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="f9509-151">RFC 6337, section 5,3 attente et reprise de médias</span><span class="sxs-lookup"><span data-stu-id="f9509-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="f9509-152">RFC autorise l’utilisation de « a = inactif », « a = sendonly », a = recvonly» pour mettre un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="f9509-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="f9509-153">Le proxy SIP prend uniquement en charge « a = inactive » et ne comprend pas si l’SBC envoie « a = sendonly » ou « a = recvonly ».</span><span class="sxs-lookup"><span data-stu-id="f9509-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="f9509-154">RFC 6337, section 5,4 «comportement lors de la réception d’un SDP avec c = 0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="f9509-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="f9509-155">[RFC3264](https://tools.ietf.org/html/rfc3264) exige qu’un agent est en mesure de recevoir SDP avec une adresse de connexion de 0.0.0.0, auquel cas cela signifie qu’aucun RTP ou RTCP ne doit être envoyé à l’homologue.</span><span class="sxs-lookup"><span data-stu-id="f9509-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="f9509-156">Le proxy SIP ne prend pas en charge cette option.</span><span class="sxs-lookup"><span data-stu-id="f9509-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="f9509-157">Modes opérationnels</span><span class="sxs-lookup"><span data-stu-id="f9509-157">Operational modes</span></span>

<span data-ttu-id="f9509-158">Il existe deux modes opérationnels pour le routage direct :</span><span class="sxs-lookup"><span data-stu-id="f9509-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="f9509-159">**Sans dérivation multimédia** dans laquelle le trafic RTP passe entre le client Teams, les processeurs multimédias et l’SBC.</span><span class="sxs-lookup"><span data-stu-id="f9509-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="f9509-160">**Avec une dérivation multimédia** dans laquelle tous les éléments MULTImédias RTP sont acheminés entre les points de terminaison d’équipes et SBC.</span><span class="sxs-lookup"><span data-stu-id="f9509-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="f9509-161">Notez que le trafic SIP passe toujours par le proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="f9509-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
