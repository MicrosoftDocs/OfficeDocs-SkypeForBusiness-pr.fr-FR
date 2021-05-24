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
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="bb896-103">Routage direct - Définitions et normes de mise en service desfc</span><span class="sxs-lookup"><span data-stu-id="bb896-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="bb896-104">Cet article décrit la façon dont Téléphone Microsoft routage système direct implémente les protocoles standard RFC.</span><span class="sxs-lookup"><span data-stu-id="bb896-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="bb896-105">Cet article est destiné aux administrateurs vocaux chargés de configurer la connexion entre le contrôleur de session en session en local (SBC) et le service proxy SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="bb896-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="bb896-106">Les interfaces SBC du client avec les composants suivants dans le Microsoft Teams principal :</span><span class="sxs-lookup"><span data-stu-id="bb896-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="bb896-107">**Proxy SIP pour** le signalisation.</span><span class="sxs-lookup"><span data-stu-id="bb896-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="bb896-108">Il s’agit du composant Internet du routage direct qui gère les connexions SIP (TLS) entre les SBCs et le routage direct.</span><span class="sxs-lookup"><span data-stu-id="bb896-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="bb896-109">**Processeurs multimédias pour** le média.</span><span class="sxs-lookup"><span data-stu-id="bb896-109">**The media processors** for media.</span></span> <span data-ttu-id="bb896-110">Il s’agit du composant Internet du routage direct qui gère le trafic de médias.</span><span class="sxs-lookup"><span data-stu-id="bb896-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="bb896-111">Ce composant utilise les protocoles SRTP et SRTCP.</span><span class="sxs-lookup"><span data-stu-id="bb896-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="bb896-112">Pour plus d’informations sur le routage direct, voir [Système téléphonique routage direct.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bb896-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="bb896-113">Pour plus d’informations sur la façon dont le routage direct implémente le protocole SIP, voir [Routage direct - Protocole SIP.](direct-routing-protocols-sip.md)</span><span class="sxs-lookup"><span data-stu-id="bb896-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="bb896-114">Normes de la norme defc</span><span class="sxs-lookup"><span data-stu-id="bb896-114">RFC standards</span></span>

<span data-ttu-id="bb896-115">Le routage direct est conforme aux normes de mise en conformité avec les normes de mise en route (RFC).</span><span class="sxs-lookup"><span data-stu-id="bb896-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="bb896-116">Le SBC connecté au routage direct doit également respecter les appels d’offre suivants (ou leurs successeurs).</span><span class="sxs-lookup"><span data-stu-id="bb896-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="bb896-117">Normes applicables aux appareils qui supportent le mode de contournement non multimédia</span><span class="sxs-lookup"><span data-stu-id="bb896-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="bb896-118">Les normes suivantes s’appliquent aux appareils qui ne supportent que le mode de contournement non multimédia :</span><span class="sxs-lookup"><span data-stu-id="bb896-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="bb896-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Protocole d’initiation de session</span><span class="sxs-lookup"><span data-stu-id="bb896-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="bb896-120">[RFC 3325.](https://www.ietf.org/rfc/rfc3325)</span><span class="sxs-lookup"><span data-stu-id="bb896-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="bb896-121">Extension privée du protocole d’initiation de session pour l’identité identitaire au sein de réseaux de confiance-sections sur la gestion de l’en-tête Identité P-1.</span><span class="sxs-lookup"><span data-stu-id="bb896-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="bb896-122">Le routage direct envoie une identité de personne avec ID de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="bb896-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="bb896-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Extension du protocole SIP (Session Initiation Protocol) pour les informations d’historique requises.</span><span class="sxs-lookup"><span data-stu-id="bb896-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="bb896-124">Voir aussi : Description du protocole SIP de routage pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="bb896-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="bb896-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Protocole d’initiation de session Referred-By mécanisme d’initiation</span><span class="sxs-lookup"><span data-stu-id="bb896-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="bb896-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) En-tête « Remplace » le protocole SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="bb896-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="bb896-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Utilisation du modèle d’offre/answer protocol (SIP) par le protocole SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="bb896-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="bb896-128">Consultez la section « Écarts par rapport à la mise en sureance de la mise en sureance de projet ».</span><span class="sxs-lookup"><span data-stu-id="bb896-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="bb896-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) et [RFC 4771.](https://tools.ietf.org/html/rfc4771)</span><span class="sxs-lookup"><span data-stu-id="bb896-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="bb896-130">Protégez le trafic RTP à l’aide du SRTP.</span><span class="sxs-lookup"><span data-stu-id="bb896-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="bb896-131">Le SBC doit être en mesure d’établir des clés à l’aide de SDES.</span><span class="sxs-lookup"><span data-stu-id="bb896-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="bb896-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Offre/clarifications de réponse au protocole SDP (Session Description Protocol) pour le multiplexage RTP/RTCP</span><span class="sxs-lookup"><span data-stu-id="bb896-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="bb896-133">Normes applicables aux appareils qui supportent le mode de dérivation média</span><span class="sxs-lookup"><span data-stu-id="bb896-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="bb896-134">En plus des normes répertoriées comme applicables au mode sans contournement, les normes suivantes sont utilisées pour le mode de dérivation média :</span><span class="sxs-lookup"><span data-stu-id="bb896-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="bb896-135">[Connectivité interactive ICE (RFC 5245 Interactive Connectivity Bypass) pour la dérivation média.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="bb896-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="bb896-136">Le SBC doit prendre en charge les états suivants :</span><span class="sxs-lookup"><span data-stu-id="bb896-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="bb896-137">ICE Lite - les clients Teams de projet sont des clients ICE complets</span><span class="sxs-lookup"><span data-stu-id="bb896-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="bb896-138">[Redémarrages DE LA GLACE.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)</span><span class="sxs-lookup"><span data-stu-id="bb896-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="bb896-139">En savoir plus sur le cas d’utilisation des redémarrages ICE et les exemples dans ICE Restart : Appel de dérivation média transféré vers un point de terminaison qui ne prend pas en charge la dérivation média</span><span class="sxs-lookup"><span data-stu-id="bb896-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="bb896-140">[Contrôle d’appel DUP (RFC RFC RFC 5589 Session Initiation Protocol) – Transfert.](https://tools.ietf.org/html/rfc5589)</span><span class="sxs-lookup"><span data-stu-id="bb896-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="bb896-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP),](https://tools.ietf.org/html/rfc3960)voir les sections 3.1, Forking et 3.2, Ringing Tone Generation</span><span class="sxs-lookup"><span data-stu-id="bb896-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="bb896-142">Utilitaires traversaux de session RFC 5389 pour NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="bb896-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="bb896-143">RFC 5766 Traversal Using Relays around NAT (TURN) : Extensions de relais aux utilitaires traversaux de session pour NAT (STUN)</span><span class="sxs-lookup"><span data-stu-id="bb896-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="bb896-144">Normes applicables à la prise en charge de la transmission des informations d’emplacement aux fournisseurs E911</span><span class="sxs-lookup"><span data-stu-id="bb896-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="bb896-145">RFC 6442, Communication d’emplacement pour le protocole d’initiation à la session</span><span class="sxs-lookup"><span data-stu-id="bb896-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="bb896-146">Écarts par rapport aux CTXT</span><span class="sxs-lookup"><span data-stu-id="bb896-146">Deviations from the RFC's</span></span>

<span data-ttu-id="bb896-147">Le tableau suivant répertorie les sections des RFC dans lesquelles l’implémentation du SIP ou de la pile multimédia par Microsoft est à partir de la norme :</span><span class="sxs-lookup"><span data-stu-id="bb896-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="bb896-148">RFC et sections</span><span class="sxs-lookup"><span data-stu-id="bb896-148">RFC and sections</span></span> | <span data-ttu-id="bb896-149">Description</span><span class="sxs-lookup"><span data-stu-id="bb896-149">Description</span></span> | <span data-ttu-id="bb896-150">Écart</span><span class="sxs-lookup"><span data-stu-id="bb896-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="bb896-151">RFC 6337, section 5.3 Hold and Resume of Media</span><span class="sxs-lookup"><span data-stu-id="bb896-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="bb896-152">La fonction RFC permet d’utiliser « a=inactive », « a=sendonly », a=recvonly » pour mettre un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="bb896-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="bb896-153">Le proxy SIP prend uniquement en charge « a=inactive » et ne comprend pas si le SBC envoie « a=sendonly » ou « a=recvonly ».</span><span class="sxs-lookup"><span data-stu-id="bb896-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="bb896-154">RFC 6337, section 5.4 « Comportement lors de la réception de SDP avec c=0.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bb896-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="bb896-155">La mise à jour [RFC3264](https://tools.ietf.org/html/rfc3264) nécessite qu’un agent soit capable de recevoir le protocole SDP avec une adresse de connexion 0.0.0.0. Dans ce cas, cela signifie que ni le RTP ni le RTCP ne doivent être envoyés à l’homologue.</span><span class="sxs-lookup"><span data-stu-id="bb896-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="bb896-156">Le proxy SIP ne prend pas en charge cette option.</span><span class="sxs-lookup"><span data-stu-id="bb896-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="bb896-157">Modes opérationnels</span><span class="sxs-lookup"><span data-stu-id="bb896-157">Operational modes</span></span>

<span data-ttu-id="bb896-158">Il existe deux modes opérationnels pour le routage direct :</span><span class="sxs-lookup"><span data-stu-id="bb896-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="bb896-159">**Sans contournement multimédia** dans lequel tout le trafic RTP circule entre le client Teams, les processeurs de média et le SBC.</span><span class="sxs-lookup"><span data-stu-id="bb896-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="bb896-160">**Avec la dérivation** média dans laquelle tous les médias RTP circulent entre Teams points de terminaison et le SBC.</span><span class="sxs-lookup"><span data-stu-id="bb896-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="bb896-161">Notez que le trafic SIP est toujours flux via le proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="bb896-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="bb896-162">DTMF</span><span class="sxs-lookup"><span data-stu-id="bb896-162">DTMF</span></span>
<span data-ttu-id="bb896-163">La pile de média DTMF n’est pas prise en charge dans la bande.</span><span class="sxs-lookup"><span data-stu-id="bb896-163">In-band DTMF is not supported by media stack.</span></span>
