---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888573"
---
# <a name="overview"></a><span data-ttu-id="5153f-103">Présentation</span><span class="sxs-lookup"><span data-stu-id="5153f-103">Overview</span></span>

<span data-ttu-id="5153f-104">Cet article décrit la façon dont le routage direct prend en charge la dérivation média avec un contrôleur de session en bordure (SBC) activé pour ICE Lite, comme décrit dans le [RFC 5245.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="5153f-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="5153f-105">Cet article est destiné aux administrateurs vocaux chargés de configurer la connexion entre le serveur SBC local et le service proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="5153f-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="5153f-106">Cet article fournit une vue d’ensemble des scénarios ICE Lite et des conditions requises pour l’interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="5153f-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="5153f-107">Cet article décrit les formats des messages et les transitions automatiques requises pour garantir la fiabilité du flux des appels et des médias.</span><span class="sxs-lookup"><span data-stu-id="5153f-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="5153f-108">Terminologie</span><span class="sxs-lookup"><span data-stu-id="5153f-108">Terminology</span></span>

- <span data-ttu-id="5153f-109">Tout d’abord Bonjour : les premiers mots prononcés par l’appelant et l’appelé.</span><span class="sxs-lookup"><span data-stu-id="5153f-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="5153f-110">Il est important que tous les efforts soient déployés pour garantir la livraison fiable des premiers paquets à partir des points de terminaison dans la plupart des cas d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="5153f-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="5153f-111">Entréeking – L’offre de l’appelant peut être proposée à plusieurs points de terminaison d’un appelant si celui-ci est disponible sur plusieurs appareils (par exemple, un utilisateur de Teams peut être connecté à Teams pour Windows et à Teams pour Android ou iPhone).</span><span class="sxs-lookup"><span data-stu-id="5153f-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="5153f-112">Réponse inversée (183) – Les points de terminaison des appelants pour une configuration d’appel plus rapide envoient une réponse avec les candidats et les clés nécessaires pour établir un flux multimédia.</span><span class="sxs-lookup"><span data-stu-id="5153f-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="5153f-113">Cela est fait dans l’attente de l’utilisateur pouvant répondre à l’appel(200OK) à partir de cette instance de l’appelant spécifique.</span><span class="sxs-lookup"><span data-stu-id="5153f-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="5153f-114">L’appelant doit être prêt à recevoir les réponses de plusieurs personnes à l’aide de la forking.</span><span class="sxs-lookup"><span data-stu-id="5153f-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="5153f-115">Re-Invite – Proposer aux candidats finux sélectionnés par le point de terminaison ICE de contrôle.</span><span class="sxs-lookup"><span data-stu-id="5153f-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="5153f-116">L’attribut a=remote-candidate permet de résoudre les conditions de course qui seraient dues à la gestion de plusieurs bifurcations.</span><span class="sxs-lookup"><span data-stu-id="5153f-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="5153f-117">Point de terminaison Teams : il peut s’agit soit d’un serveur (processeur multimédia, relais de transport) soit du client Teams.</span><span class="sxs-lookup"><span data-stu-id="5153f-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="5153f-118">Format des messages</span><span class="sxs-lookup"><span data-stu-id="5153f-118">Message format</span></span>

<span data-ttu-id="5153f-119">L’infrastructure Teams suit le RFC 5245 pour ICE-Lite.</span><span class="sxs-lookup"><span data-stu-id="5153f-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="5153f-120">Cela implique que tous les messages STUN respectent la [norme RFC 5389.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="5153f-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="5153f-121">Les STUN requis par la mise à jour RFC 5389 doivent ignorer les attributs STUN qu’ils ne reconnaissent pas et continuer à traiter les messages avec les attributs connus.</span><span class="sxs-lookup"><span data-stu-id="5153f-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="5153f-122">Si des paquets malformés sont reçus, les paquets doivent être ignorés sans impact sur l’établissement de la session multimédia.</span><span class="sxs-lookup"><span data-stu-id="5153f-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="5153f-123">Conditions requises pour ICE Lite</span><span class="sxs-lookup"><span data-stu-id="5153f-123">ICE Lite requirements</span></span>

<span data-ttu-id="5153f-124">Cette section présente brièvement les conditions requises pour ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="5153f-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="5153f-125">Rassemblement des candidats</span><span class="sxs-lookup"><span data-stu-id="5153f-125">Candidate gathering</span></span>

<span data-ttu-id="5153f-126">Le SBC doit offrir un seul candidat accessible publiquement.</span><span class="sxs-lookup"><span data-stu-id="5153f-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="5153f-127">Pour l’instant, seuls les candidats IPV4 sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="5153f-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="5153f-128">Vérifications de connectivité</span><span class="sxs-lookup"><span data-stu-id="5153f-128">Connectivity checks</span></span>

<span data-ttu-id="5153f-129">L’implémentation ICE Lite doit répondre aux vérifications de connectivité reçues.</span><span class="sxs-lookup"><span data-stu-id="5153f-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="5153f-130">Le point de terminaison ICE Lite ne doit pas envoyer de demandes de vérification de la connectivité.</span><span class="sxs-lookup"><span data-stu-id="5153f-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="5153f-131">(Si des vérifications de connectivité sont envoyées en violation, l’implémentation complète répondra, ce qui peut entraîner la découverte de candidats dérivé par des pairs inattendus et potentiellement entraîner des échecs d’appel.)</span><span class="sxs-lookup"><span data-stu-id="5153f-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="5153f-132">Tous les autres peuvent y avoir été nommé</span><span class="sxs-lookup"><span data-stu-id="5153f-132">Nominations</span></span>

<span data-ttu-id="5153f-133">Le point de terminaison d’implémentation complète ICE sera toujours le point de terminaison contrôle et suit les règles « Regular » pour la sélection des candidats finaux à utiliser pour le flux de médias.</span><span class="sxs-lookup"><span data-stu-id="5153f-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="5153f-134">Le point de terminaison ICE Lite peut utiliser les contrôles pour terminer le chemin à utiliser pour établir un appel multimédia et complet.</span><span class="sxs-lookup"><span data-stu-id="5153f-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="5153f-135">Remarque : en cas d’utilisation d’une pliure avec des points de terminaison d’égal à égal envoyant 183 réponses différentes, le SBC doit être prêt à répondre aux vérifications de plusieurs points de terminaison et également à partir de plusieurs points de terminaison si les problèmes ont lieu avant 200OK.</span><span class="sxs-lookup"><span data-stu-id="5153f-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="5153f-136">Selon la fusion de l’ordinateur de l’état ICE sur le chemin d’accès final et le minutage de la réponse de l’utilisateur, les choses peuvent se produire avant ou après 200OK.</span><span class="sxs-lookup"><span data-stu-id="5153f-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="5153f-137">Le SBC doit être en mesure de gérer ces deux cas.</span><span class="sxs-lookup"><span data-stu-id="5153f-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="5153f-138">Convergeant pour l’king</span><span class="sxs-lookup"><span data-stu-id="5153f-138">Converging for forking</span></span>

<span data-ttu-id="5153f-139">Si l’offre SBC est duplication avec plusieurs points de terminaison Teams, les points de terminaison Teams peuvent répondre avec une réponse insé immédiate et démarrer des vérifications de connectivité.</span><span class="sxs-lookup"><span data-stu-id="5153f-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="5153f-140">Le SBC doit être prêt à recevoir les vérifications de connectivité et à répondre aux vérifications de connectivité à partir de plusieurs points de terminaison d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="5153f-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="5153f-141">Par exemple, l’utilisateur de Teams peut être à la fois inscrit à un ordinateur de bureau et à un téléphone portable.</span><span class="sxs-lookup"><span data-stu-id="5153f-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="5153f-142">Les deux appareils seront avertis de l’appel entrant et tenteront de vérifier la connectivité avec le SBC.</span><span class="sxs-lookup"><span data-stu-id="5153f-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="5153f-143">Finalement, un seul point de terminaison répondra à l’appel (200OK).</span><span class="sxs-lookup"><span data-stu-id="5153f-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="5153f-144">Lors de la réception de la 200OK, le SBC peut configurer le contexte exact pour le traitement des paquets multimédias.</span><span class="sxs-lookup"><span data-stu-id="5153f-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="5153f-145">Scénarios</span><span class="sxs-lookup"><span data-stu-id="5153f-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="5153f-146">Appel entrant à partir de SBC</span><span class="sxs-lookup"><span data-stu-id="5153f-146">Inbound call from SBC</span></span>

<span data-ttu-id="5153f-147">Dans ce scénario, le SBC doit gérer plusieurs points de terminaison pairs possibles :</span><span class="sxs-lookup"><span data-stu-id="5153f-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="5153f-148">Les points de terminaison du serveur répondront généralement directement avec 200OK.</span><span class="sxs-lookup"><span data-stu-id="5153f-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="5153f-149">Il s’agit de points de terminaison ICE complets qui sont généralement impliqués dans des scénarios de messagerie vocale, de file d’attente d’appels et de attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="5153f-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="5153f-150">Les points de terminaison du client peuvent envoyer plusieurs réponses avec différentes balises De/À (183) suivies d’un 200OK à partir du point de terminaison qui répond à l’appel.</span><span class="sxs-lookup"><span data-stu-id="5153f-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="5153f-151">Il s’agit de points de terminaison ICE complets représentant généralement des clients d’utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="5153f-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="5153f-152">Autres points de terminaison SBC.</span><span class="sxs-lookup"><span data-stu-id="5153f-152">Other SBC endpoints.</span></span> <span data-ttu-id="5153f-153">Il s’agit des points de terminaison ICE Lite généralement impliqués dans le scénario de sonnerie simultanée des points de terminaison du client et d’autres numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="5153f-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="5153f-154">Le SBC doit répondre à toutes les demandes de vérification de connectivité valides reçues à partir des points de terminaison ICE complets.</span><span class="sxs-lookup"><span data-stu-id="5153f-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="5153f-155">Selon la technologie RFC, les points de terminaison ICE complets deviendront des points de terminaison contrôlés.</span><span class="sxs-lookup"><span data-stu-id="5153f-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="5153f-156">Les points de terminaison Teams (client/serveur) effectuent des vérifications de connectivité « régulières ».</span><span class="sxs-lookup"><span data-stu-id="5153f-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="5153f-157">Le 200Ok final peut être soit à partir d’un point de terminaison qui a envoyé des médias précoces, soit d’un autre point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="5153f-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="5153f-158">Lors de la réception de la 200Ok, le SBC doit configurer le contexte pour le flux de médias.</span><span class="sxs-lookup"><span data-stu-id="5153f-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="5153f-159">Médias précoces</span><span class="sxs-lookup"><span data-stu-id="5153f-159">Early media</span></span>

<span data-ttu-id="5153f-160">S’il existe un flux multimédia en avant-première, le SBC doit se trouver au premier point de terminaison qui démarre la diffusion en continu de médias. un flux de médias peut commencer avant les candidats.</span><span class="sxs-lookup"><span data-stu-id="5153f-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="5153f-161">Le SBC doit prendre en charge l’envoi de DTMF au cours de cette phase afin d’activer les scénarios DVR/messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="5153f-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="5153f-162">Le SBC doit utiliser le chemin de priorité le plus élevé sur lequel il a reçu les vérifications si l’examen n’est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="5153f-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="5153f-163">Appel sortant vers SBC</span><span class="sxs-lookup"><span data-stu-id="5153f-163">Outbound call to SBC</span></span>

<span data-ttu-id="5153f-164">Les points de terminaison Teams sont l’appelant pour ce scénario et seront les points de terminaison de contrôle.</span><span class="sxs-lookup"><span data-stu-id="5153f-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="5153f-165">Lors de la réception d’une réponse complète (183) ou d’une réponse finale (200OK), le point de terminaison Teams démarre les vérifications de connectivité et passe aux vérifications de connectivité « régulières » pour effectuer les vérifications de connectivité.</span><span class="sxs-lookup"><span data-stu-id="5153f-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="5153f-166">Remarque : si la base de données SBC envoie une réponse complète (183), le SBC doit être prêt à recevoir les demandes de vérification de connectivité et potentiellement terminer les vérifications avant l’envoi du 200OK par le SBC.</span><span class="sxs-lookup"><span data-stu-id="5153f-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="5153f-167">Si les vérifications et/ou les contrôles sont effectués avant la réception du 200OK, les vérifications et/ou contrôles ne seront pas effectués à nouveau après la réception de 200OK.</span><span class="sxs-lookup"><span data-stu-id="5153f-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="5153f-168">Le SBC ne doit pas changer les candidats ICE, le mot de passe et le ufrag (fragment de nom d’utilisateur) entre 183 et 200.</span><span class="sxs-lookup"><span data-stu-id="5153f-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="5153f-169">Pour prendre en charge les fichiers multimédias en avant-première, le SBC peut commencer à diffuser les médias vers le candidat ICE de l’pair, avec la priorité la plus élevée en fonction des vérifications de connectivité reçues, avant même que les points de terminaison Teams ne soient terminés.</span><span class="sxs-lookup"><span data-stu-id="5153f-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="5153f-170">Le SBC doit s’attendre à un support de Teams sur n’importe quel candidat jusqu’à ce que l’équipe soit terminée.</span><span class="sxs-lookup"><span data-stu-id="5153f-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="5153f-171">Une fois qu’un candidat a été désigné, le contexte doit être réinitialisé pour envoyer et recevoir des paquets multimédias.</span><span class="sxs-lookup"><span data-stu-id="5153f-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="5153f-172">Conditions requises de prise en charge du SRTP</span><span class="sxs-lookup"><span data-stu-id="5153f-172">SRTP support requirements</span></span>

<span data-ttu-id="5153f-173">Le code SBC doit prendre en charge les données de chiffrement SRTP AES_CM_128_HMAC_SHA1_80'offre et de réponse dans le format suivant :</span><span class="sxs-lookup"><span data-stu-id="5153f-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="5153f-174">Voici un exemple d’attribut crypto dans l’offre SDP provenant du SBC :</span><span class="sxs-lookup"><span data-stu-id="5153f-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="5153f-175">Les paramètres MKI et Longueur ne sont pas obligatoires.</span><span class="sxs-lookup"><span data-stu-id="5153f-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="5153f-176">Pour plus d’informations, [voir RFC 4568, section 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="5153f-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="5153f-177">Conditions requises pour la prise en charge de SDES</span><span class="sxs-lookup"><span data-stu-id="5153f-177">SDES support requirements</span></span>

<span data-ttu-id="5153f-178">L’appareil doit pouvoir proposer SDES dans le format décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="5153f-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="5153f-179">Les processeurs Microsoft Media préfèrent toujours SDES.</span><span class="sxs-lookup"><span data-stu-id="5153f-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="5153f-180">Avec une dérivation non multimédia, même si un client prend uniquement en charge DTLS, les processeurs multimédias sont convertis en SDES.</span><span class="sxs-lookup"><span data-stu-id="5153f-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="5153f-181">Avec la dérivation média, si un client est DTLS uniquement (état Google Chrome futur), un routage direct insère un mp dans le chemin, convertissant l’appel de la dérivation média en contournement non multimédia.</span><span class="sxs-lookup"><span data-stu-id="5153f-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="5153f-182">Entre le composant SBC et le composant de processeur multimédia du routage direct, SDES est toujours utilisé.</span><span class="sxs-lookup"><span data-stu-id="5153f-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="5153f-183">Pour l’instant, aucun client Teams ne propose uniquement les DTLS ; Google a toutefois annoncé qu’à un moment donné, il cessera de le faire.</span><span class="sxs-lookup"><span data-stu-id="5153f-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="5153f-184">Format de l’offre SBC en mode contournement</span><span class="sxs-lookup"><span data-stu-id="5153f-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="5153f-185">L’offre doit contenir SDES et peut contenir des contenus DTLS facultatifs au format suivant :</span><span class="sxs-lookup"><span data-stu-id="5153f-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="5153f-186">Format de réponse contenant SDES à SBC</span><span class="sxs-lookup"><span data-stu-id="5153f-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="5153f-187">Format de l’offre de Teams vers SBC</span><span class="sxs-lookup"><span data-stu-id="5153f-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="5153f-188">Format de l’offre SDES uniquement sur SBC</span><span class="sxs-lookup"><span data-stu-id="5153f-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

