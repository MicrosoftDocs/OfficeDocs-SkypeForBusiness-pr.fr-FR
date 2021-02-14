---
title: Basculement de jonction sur les appels sortants
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lisez cette rubrique pour découvrir comment gérer les failovers de ligne dans les appels sortants de Teams vers le contrôleur de session en bordure (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836176"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="153a8-103">Basculement de jonction sur les appels sortants</span><span class="sxs-lookup"><span data-stu-id="153a8-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="153a8-104">Cette rubrique explique comment éviter les failovers de ligne dans les appels sortants, de Teams au contrôleur de session en bordure (SBC).</span><span class="sxs-lookup"><span data-stu-id="153a8-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="153a8-105">Failover on network errors</span><span class="sxs-lookup"><span data-stu-id="153a8-105">Failover on network errors</span></span>

<span data-ttu-id="153a8-106">Si, pour une raison quelconque, une ligne ne peut pas être connectée, la connexion à la même ligne est essayée à partir d’un autre centre de données Microsoft.</span><span class="sxs-lookup"><span data-stu-id="153a8-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="153a8-107">Par exemple, une ligne n’est peut-être pas connectée si une connexion est refusée, s’il y a un délai d’émission du TLS ou s’il existe d’autres problèmes au niveau du réseau.</span><span class="sxs-lookup"><span data-stu-id="153a8-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="153a8-108">Par exemple, une connexion peut échouer si un administrateur limite l’accès au SBC uniquement à partir d’adresses IP connues, mais oublie de placer les adresses IP de tous les centres de données de routage Microsoft Direct sur la liste de contrôle d’accès (ACL) du SBC.</span><span class="sxs-lookup"><span data-stu-id="153a8-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="153a8-109">Over de codes SIP spécifiques reçus du contrôleur de bordure de session (SBC)</span><span class="sxs-lookup"><span data-stu-id="153a8-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="153a8-110">Si le routage direct reçoit des codes d’erreur 4xx ou 6xx SIP en réponse à une invitation sortante, l’appel est considéré comme terminé par défaut.</span><span class="sxs-lookup"><span data-stu-id="153a8-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="153a8-111">Sortant désigne un appel entre un client Teams et le réseau téléphonique public commuté (RST) avec le flux de trafic suivant : Client Teams -> Routage direct -> SBC -> Réseau téléphonique.</span><span class="sxs-lookup"><span data-stu-id="153a8-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="153a8-112">La liste des codes SIP est disponibles dans la mise à [l’essai (SIP) RFC (Session Initiation Protocol).](https://tools.ietf.org/html/rfc3261)</span><span class="sxs-lookup"><span data-stu-id="153a8-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="153a8-113">Supposons qu’un SBC a répondu à une invitation entrante avec le code « Délai d’appel 408 : le serveur ne pouvait pas produire de réponse dans un délai approprié, par exemple, s’il ne pouvait pas déterminer l’emplacement de l’utilisateur à temps.</span><span class="sxs-lookup"><span data-stu-id="153a8-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="153a8-114">Le client PEUT répéter la demande sans modification ultérieurement ».</span><span class="sxs-lookup"><span data-stu-id="153a8-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="153a8-115">Ce SBC particulier peut avoir des difficultés de connexion au contact de l’appelant, peut-être en raison d’une configuration réseau mal configurée ou d’une autre erreur.</span><span class="sxs-lookup"><span data-stu-id="153a8-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="153a8-116">Toutefois, il existe un autre SBC dans l’itinéraire, qui pourra peut-être joindre l’appelé.</span><span class="sxs-lookup"><span data-stu-id="153a8-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="153a8-117">Dans le diagramme suivant, lorsqu’un utilisateur appelle un numéro de téléphone, deux SCS peuvent potentiellement remettre cet appel dans l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="153a8-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="153a8-118">Au début, SBC1.contoso.com est sélectionné pour l’appel, mais SBC1.contoso.com n’est pas en mesure d’accéder à un réseau PTSN en raison d’un problème de réseau.</span><span class="sxs-lookup"><span data-stu-id="153a8-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="153a8-119">Par défaut, l’appel sera effectué à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="153a8-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagramme montrant SBC ne parvient pas à joindre PSTN en raison d’un problème de réseau](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="153a8-121">Mais il existe un autre SBC dans l’itinéraire, qui peut potentiellement donner l’appel.</span><span class="sxs-lookup"><span data-stu-id="153a8-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="153a8-122">Si vous configurez le paramètre, le deuxième SBC sera essayé, comme SBC2.contoso.com `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="153a8-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagramme montrant le routage vers le deuxième SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="153a8-124">La définition du paramètre -FailoverResponseCodes et la spécification des codes vous permettent d’affiner votre routage et d’éviter les problèmes potentiels lorsqu’un SBC ne peut pas passer d’appel en raison de problèmes de réseau ou autres.</span><span class="sxs-lookup"><span data-stu-id="153a8-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="153a8-125">Valeurs par défaut : 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="153a8-125">Default values:  408, 503, 504</span></span>

