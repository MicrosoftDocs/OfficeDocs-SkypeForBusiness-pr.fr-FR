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
description: Protocoles de routage directe
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f21a4532a841a23f6bbb78a57e223616ae539fa
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835134"
---
# <a name="overview"></a><span data-ttu-id="e2056-103">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="e2056-103">Overview</span></span>

<span data-ttu-id="e2056-104">Cet article décrit comment le routage direct prend en charge la dérivation multimédia avec un contrôleur de bordure de session (SBC) activé pour ICE Lite, comme décrit dans [RFC 5245](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="e2056-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="e2056-105">Cet article est destiné aux administrateurs de voix qui sont responsables de la configuration de la connexion entre le SBC local et le service proxy SIP.</span><span class="sxs-lookup"><span data-stu-id="e2056-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="e2056-106">Cet article fournit une vue d’ensemble des scénarios et des exigences relatives à l’interopérabilité de glace Lite.</span><span class="sxs-lookup"><span data-stu-id="e2056-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="e2056-107">Cet article décrit les formats des messages et les transitions de machine à États requises pour garantir la fiabilité des appels et du flux multimédia.</span><span class="sxs-lookup"><span data-stu-id="e2056-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="e2056-108">Liée</span><span class="sxs-lookup"><span data-stu-id="e2056-108">Terminology</span></span>

- <span data-ttu-id="e2056-109">Tout d’abord, Voici les premiers mots prononcés par l’appelant et l’appelé.</span><span class="sxs-lookup"><span data-stu-id="e2056-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="e2056-110">Il est important de veiller à ce que toutes les tâches soient apportées pour s’assurer que les premiers paquets des points de terminaison sont remis de façon fiable dans la plupart des cas d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="e2056-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="e2056-111">Bifurcation : l’offre de l’appelant peut être fournie aux points de terminaison des appelants si l’appel est disponible sur plusieurs appareils (par exemple, un utilisateur de teams est peut-être connecté à teams pour Windows et Teams pour Android ou iPhone).</span><span class="sxs-lookup"><span data-stu-id="e2056-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="e2056-112">Réponse provisoire (183) : les points de terminaison des appelants pour une configuration plus rapide des appels envoient une réponse avec les candidats et les clés nécessaires à la création du flux multimédia.</span><span class="sxs-lookup"><span data-stu-id="e2056-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="e2056-113">Cette opération est réalisée en prévision de l’utilisateur qui peut éventuellement répondre à l’appel (200OK) de cette instance d’un appel.</span><span class="sxs-lookup"><span data-stu-id="e2056-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="e2056-114">Avec la bifurcation, l’appelant doit être prêt à recevoir plusieurs réponses provisoires.</span><span class="sxs-lookup"><span data-stu-id="e2056-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="e2056-115">Re-invitation : une proposition avec les candidats finaux sélectionnés par le point de terminaison de contrôle de glace.</span><span class="sxs-lookup"><span data-stu-id="e2056-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="e2056-116">Cette opération a pour assembler l’attribut a = candidat à distance et résoudre les conditions de concurrence après la gestion de plusieurs branches.</span><span class="sxs-lookup"><span data-stu-id="e2056-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="e2056-117">Point de terminaison d’équipes : il peut s’agir d’un serveur (processeur de média, relais de transport) ou du client Teams.</span><span class="sxs-lookup"><span data-stu-id="e2056-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="e2056-118">Format des messages</span><span class="sxs-lookup"><span data-stu-id="e2056-118">Message format</span></span>

<span data-ttu-id="e2056-119">L’infrastructure teams suit le RFC 5245 pour glace-Lite.</span><span class="sxs-lookup"><span data-stu-id="e2056-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="e2056-120">Cela implique que tous les messages STUN soient conformes à [RFC 5389](https://tools.ietf.org/html/rfc5389).</span><span class="sxs-lookup"><span data-stu-id="e2056-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="e2056-121">Le SBCs tel qu’il est requis par RFC 5389 doit ignorer tout attribut STUN qu’il ne reconnaît pas, et continuer de traiter les messages avec les attributs connus.</span><span class="sxs-lookup"><span data-stu-id="e2056-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="e2056-122">En cas de réception de paquets incorrects, les paquets doivent être supprimés sans impact sur l’établissement de la session multimédia.</span><span class="sxs-lookup"><span data-stu-id="e2056-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="e2056-123">Configuration requise pour glace Lite</span><span class="sxs-lookup"><span data-stu-id="e2056-123">ICE Lite requirements</span></span>

<span data-ttu-id="e2056-124">Cette section décrit brièvement la configuration requise pour ICE Lite.</span><span class="sxs-lookup"><span data-stu-id="e2056-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="e2056-125">Rassemblement des candidats</span><span class="sxs-lookup"><span data-stu-id="e2056-125">Candidate gathering</span></span>

<span data-ttu-id="e2056-126">La SBC doit fournir un seul candidat qui est publiquement joignable.</span><span class="sxs-lookup"><span data-stu-id="e2056-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="e2056-127">Pour l’instant, seuls les candidats IPV4 sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e2056-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="e2056-128">Vérification de la connectivité</span><span class="sxs-lookup"><span data-stu-id="e2056-128">Connectivity checks</span></span>

<span data-ttu-id="e2056-129">L’implémentation de ICE Lite doit répondre aux vérifications de connectivité reçues.</span><span class="sxs-lookup"><span data-stu-id="e2056-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="e2056-130">Le point de terminaison ICE Lite ne doit pas envoyer de demandes de vérification de connectivité.</span><span class="sxs-lookup"><span data-stu-id="e2056-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="e2056-131">(Si des vérifications de connectivité sont envoyées en violation, l’implémentation complète répondra, ce qui peut entraîner la découverte d’candidats inattendus et provoquer potentiellement des échecs d’appel.)</span><span class="sxs-lookup"><span data-stu-id="e2056-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="e2056-132">Candidatures</span><span class="sxs-lookup"><span data-stu-id="e2056-132">Nominations</span></span>

<span data-ttu-id="e2056-133">Le point de terminaison de l’implémentation complète de ICE sera toujours le point de terminaison de contrôle, et suivreez les désignations « standard » pour sélectionner les candidats finaux à utiliser pour le flux multimédia.</span><span class="sxs-lookup"><span data-stu-id="e2056-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="e2056-134">Le point de terminaison Lite Lite peut utiliser les candidatures pour conclure le chemin à utiliser pour le média et l’établissement d’appel complet.</span><span class="sxs-lookup"><span data-stu-id="e2056-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="e2056-135">Remarque : dans le cas d’une bifurcation avec des points de terminaison d’homologues qui envoient des réponses provisoires 183, l’SBC doit être prêt à répondre aux contrôles de plusieurs points de terminaison et aux désignations de plusieurs points de terminaison si les candidatures se produisent avant 200OK.</span><span class="sxs-lookup"><span data-stu-id="e2056-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="e2056-136">En fonction de la convergence de la machine à États de glace sur le chemin final et le minutage de la réponse de l’utilisateur, les candidatures peuvent se produire avant ou après 200OK.</span><span class="sxs-lookup"><span data-stu-id="e2056-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="e2056-137">L’SBC doit être en mesure de gérer les deux cas.</span><span class="sxs-lookup"><span data-stu-id="e2056-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="e2056-138">Convergence pour la bifurcation</span><span class="sxs-lookup"><span data-stu-id="e2056-138">Converging for forking</span></span>

<span data-ttu-id="e2056-139">S’il s’agit d’une proposition de branches SBC à plusieurs points de terminaison d’équipes, les points de terminaison d’équipes pourront répondre avec une réponse provisoire et démarrer des vérifications de connectivité.</span><span class="sxs-lookup"><span data-stu-id="e2056-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="e2056-140">L’SBC doit être prêt à recevoir des vérifications de connectivité et à répondre aux vérifications de connectivité provenant de multiples points de terminaison d’homologues.</span><span class="sxs-lookup"><span data-stu-id="e2056-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="e2056-141">Par exemple, l’utilisateur d’équipes peut être connecté à la fois à un bureau et un téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="e2056-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="e2056-142">Les deux périphériques seront avertis de l’appel entrant et tenteront de vérifier la connectivité avec l’SBC.</span><span class="sxs-lookup"><span data-stu-id="e2056-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="e2056-143">Pour le moment, seul l’un des points de terminaison répond à l’appel (200OK).</span><span class="sxs-lookup"><span data-stu-id="e2056-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="e2056-144">Lors de la réception de 200OK, l’SBC peut définir le contexte approprié pour le traitement des paquets multimédias.</span><span class="sxs-lookup"><span data-stu-id="e2056-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="e2056-145">Scénarios</span><span class="sxs-lookup"><span data-stu-id="e2056-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="e2056-146">Appel entrant d’SBC</span><span class="sxs-lookup"><span data-stu-id="e2056-146">Inbound call from SBC</span></span>

<span data-ttu-id="e2056-147">Pour ce scénario, l’SBC doit gérer plusieurs points de terminaison homologues :</span><span class="sxs-lookup"><span data-stu-id="e2056-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="e2056-148">Les points de terminaison du serveur répondent généralement directement à 200OK.</span><span class="sxs-lookup"><span data-stu-id="e2056-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="e2056-149">Il s’agit de points de terminaison de glace complète qui sont généralement impliqués dans les scénarios de boîte vocale, de files d’attente d’appels et de standard automatique.</span><span class="sxs-lookup"><span data-stu-id="e2056-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="e2056-150">Les points de terminaison client peuvent envoyer plusieurs réponses provisoires avec différentes balises (183) suivies d’une 200OK à partir du point de terminaison qui répond à l’appel.</span><span class="sxs-lookup"><span data-stu-id="e2056-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="e2056-151">Il s’agit de points de terminaison de type glace complets qui représentent généralement les clients des utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="e2056-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="e2056-152">Autres points de terminaison SBC.</span><span class="sxs-lookup"><span data-stu-id="e2056-152">Other SBC endpoints.</span></span> <span data-ttu-id="e2056-153">Il s’agit de points de terminaison ICE Lite habituellement liés au scénario de sonnerie simultanée de points de terminaison client et d’autres numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="e2056-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="e2056-154">L’SBC doit répondre à toutes les demandes de vérification de connectivité valides reçues des points de terminaison de la glace complète.</span><span class="sxs-lookup"><span data-stu-id="e2056-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="e2056-155">Par RFC, les points de terminaison de la glace complète sont en gestion des points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="e2056-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="e2056-156">Les points de terminaison Teams (client/serveur) effectuent des nominations « standard » pour vérifier la connectivité.</span><span class="sxs-lookup"><span data-stu-id="e2056-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="e2056-157">Le 200Ok final peut être à partir d’un point de terminaison qui a envoyé des éléments multimédias en avance ou à partir d’un point de terminaison différent.</span><span class="sxs-lookup"><span data-stu-id="e2056-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="e2056-158">Lors de la réception de 200Ok, l’SBC doit configurer le contexte approprié pour le flux multimédia.</span><span class="sxs-lookup"><span data-stu-id="e2056-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="e2056-159">Premiers éléments multimédias</span><span class="sxs-lookup"><span data-stu-id="e2056-159">Early media</span></span>

<span data-ttu-id="e2056-160">S’il y a un flux de média précoce, l’SBC doit se verrouiller sur le premier point de terminaison qui démarre le média de diffusion. le flux multimédia peut commencer avant que les candidats soient désignés.</span><span class="sxs-lookup"><span data-stu-id="e2056-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="e2056-161">L’SBC doit avoir une prise en charge pour l’envoi d’un DTMF dans le cadre de cette phase pour activer les scénarios IVR/vocaux.</span><span class="sxs-lookup"><span data-stu-id="e2056-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="e2056-162">L’SBC doit utiliser le chemin de priorité le plus élevé sur lequel il a reçu des vérifications si la candidature n’est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="e2056-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="e2056-163">Appel sortant vers SBC</span><span class="sxs-lookup"><span data-stu-id="e2056-163">Outbound call to SBC</span></span>

<span data-ttu-id="e2056-164">Les points de terminaison d’équipes sont l’appelant pour ce scénario et seront le point de terminaison de contrôle.</span><span class="sxs-lookup"><span data-stu-id="e2056-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="e2056-165">Lors de la réception d’une réponse provisoire (183) ou d’une réponse finale (200OK), le point de terminaison d’équipe démarre le contrôle de la connectivité et passe à l’étape « standard » pour terminer les vérifications de connectivité.</span><span class="sxs-lookup"><span data-stu-id="e2056-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="e2056-166">Remarque : si la SBC envoie une réponse provisoire (183), l’SBC doit être prêt à recevoir des requêtes de vérification de connectivité et peut éventuellement terminer les candidatures avant que le 200OK ne soit envoyé par l’SBC.</span><span class="sxs-lookup"><span data-stu-id="e2056-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="e2056-167">Si les vérifications et/ou nominations sont achevées avant la réception de 200OK, les vérifications et/ou les nominations ne seront pas effectuées de nouveau après réception de 200OK.</span><span class="sxs-lookup"><span data-stu-id="e2056-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="e2056-168">L’SBC ne doit pas modifier les candidatures de glace, le mot de passe et ufrag (fragment de nom d’utilisateur) entre 183 et 200.</span><span class="sxs-lookup"><span data-stu-id="e2056-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="e2056-169">Pour prendre en charge les contenus multimédias, les SBC peuvent commencer à diffuser en continu le contenu multimédia du candidat à la glace pair, avec la plus grande priorité en fonction des vérifications de connectivité reçues, même avant la fin de la nomination par le point de terminaison d’équipe.</span><span class="sxs-lookup"><span data-stu-id="e2056-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="e2056-170">Les SBC doivent s’attendre à ce que le contenu multimédia d’équipes soit éligible jusqu’à ce que les candidatures soient terminées.</span><span class="sxs-lookup"><span data-stu-id="e2056-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="e2056-171">Une fois qu’un candidat est désigné, l’élément SBC doit réinitialiser le contexte approprié pour envoyer et recevoir des paquets multimédias.</span><span class="sxs-lookup"><span data-stu-id="e2056-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="e2056-172">SRTP requises du support technique</span><span class="sxs-lookup"><span data-stu-id="e2056-172">SRTP support requirements</span></span>

<span data-ttu-id="e2056-173">L’SBC doit prendre en charge le chiffrement de chiffrement SRTP AES_CM_128_HMAC_SHA1_80 pour les propositions et répondez aux formats suivants :</span><span class="sxs-lookup"><span data-stu-id="e2056-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="e2056-174">Vous trouverez ci-dessous un exemple de l’attribut crypto de l’offrant SDP de l’SBC :</span><span class="sxs-lookup"><span data-stu-id="e2056-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="e2056-175">Les paramètres de MKI et de longueur ne sont pas obligatoires.</span><span class="sxs-lookup"><span data-stu-id="e2056-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="e2056-176">Pour plus d’informations, reportez-vous au [RFC 4568, section 6,1](https://tools.ietf.org/html/rfc4568#section-6.1).</span><span class="sxs-lookup"><span data-stu-id="e2056-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="e2056-177">Configuration requise pour le support SDES</span><span class="sxs-lookup"><span data-stu-id="e2056-177">SDES support requirements</span></span>

<span data-ttu-id="e2056-178">L’appareil doit être en mesure d’afficher SDES dans le format décrit ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e2056-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="e2056-179">Les processeurs multimédias Microsoft préfèrent toujours SDES.</span><span class="sxs-lookup"><span data-stu-id="e2056-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="e2056-180">Dans le cas d’une dérivation non multimédia, même si un client prend uniquement en charge DTLS, les processeurs de médias sont convertis en SDES.</span><span class="sxs-lookup"><span data-stu-id="e2056-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="e2056-181">Dans le cadre d’une dérivation de média, si un client est DTLS uniquement (État Google Chrome à venir), le routage direct insérera un MP dans le chemin d’accès, en convertissant l’appel à partir d’une dérivation média en non multimédia.</span><span class="sxs-lookup"><span data-stu-id="e2056-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="e2056-182">Entre le composant SBC et le processeur multimédia du routage direct, SDES est toujours utilisé.</span><span class="sxs-lookup"><span data-stu-id="e2056-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="e2056-183">Pour le moment, il n’y a pas de client d’équipe qui propose uniquement DTLS ; Néanmoins, Google a annoncé qu’à un moment donné, il ne prend plus en charge SDES.</span><span class="sxs-lookup"><span data-stu-id="e2056-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="e2056-184">Format de l’offrant proposée par SBC en mode contournement</span><span class="sxs-lookup"><span data-stu-id="e2056-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="e2056-185">L’option doit contenir SDES et contenir DTLS facultatif dans le format suivant :</span><span class="sxs-lookup"><span data-stu-id="e2056-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="e2056-186">Format de la réponse contenant SDES à SBC</span><span class="sxs-lookup"><span data-stu-id="e2056-186">Format for answer containing SDES to SBC</span></span>

```
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="e2056-187">Mettre en forme les propositions d’équipes en SBC</span><span class="sxs-lookup"><span data-stu-id="e2056-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="e2056-188">Format de la présentation pour les services SBC uniquement</span><span class="sxs-lookup"><span data-stu-id="e2056-188">Format for SDES only offer to SBC</span></span>

```
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

