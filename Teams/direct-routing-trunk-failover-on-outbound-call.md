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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Apprenez-en davantage sur la gestion des basculements de Trunk pour les appels sortants de teams vers le contrôleur de bordure de session (SBC).
ms.openlocfilehash: e9efcfba696886c0fc4885778b79832956ccb893
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290362"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="d163d-103">Basculement de jonction sur les appels sortants</span><span class="sxs-lookup"><span data-stu-id="d163d-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="d163d-104">Cette rubrique explique comment éviter le basculement de Trunk sur les appels sortants à partir d’équipes vers le contrôleur de bordure de session (SBC).</span><span class="sxs-lookup"><span data-stu-id="d163d-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="d163d-105">Basculement sur erreur réseau</span><span class="sxs-lookup"><span data-stu-id="d163d-105">Failover on network errors</span></span>

<span data-ttu-id="d163d-106">Si un Trunk ne peut pas être connecté pour une raison quelconque, la connexion au même Trunk sera tentée à partir d’un autre centre de donnée Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d163d-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="d163d-107">Un Trunk n’est peut-être pas connecté, par exemple, si une connexion est refusée, s’il y a un délai de connexion TLS ou s’il existe d’autres problèmes liés au réseau.</span><span class="sxs-lookup"><span data-stu-id="d163d-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="d163d-108">Par exemple, une connexion peut échouer si un administrateur limite l’accès à l’SBC uniquement à partir d’adresses IP bien connues, mais oublie de placer les adresses IP de tous les centres de distribution de routage direct Microsoft dans la liste de contrôle d’accès (ACL) de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="d163d-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="d163d-109">Basculement de codes SIP spécifiques reçus du contrôleur de bordure de session (SBC)</span><span class="sxs-lookup"><span data-stu-id="d163d-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="d163d-110">Si le routage direct reçoit des codes d’erreur SIP 4xx ou 6xx en réponse à une invitation sortante, l’appel est considéré comme complet par défaut.</span><span class="sxs-lookup"><span data-stu-id="d163d-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="d163d-111">Sortant désigne un appel d’un client teams vers le réseau téléphonique public commuté (RTC) avec le flux de trafic suivant: teams client-> direct-> SBC-> de réseau téléphonique.</span><span class="sxs-lookup"><span data-stu-id="d163d-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="d163d-112">La liste des codes SIP est disponible dans le [RFC SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="d163d-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="d163d-113">Dans le cas contraire, une colonie a répondu à une invitation entrante avec le code «408 de demande d’expiration: le serveur n’a pas pu produire de réponse dans un délai approprié, par exemple, s’il n’a pas pu déterminer l’emplacement de l’utilisateur dans le temps.</span><span class="sxs-lookup"><span data-stu-id="d163d-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="d163d-114">Le client risque de reproduire la demande sans modification ultérieurement.»</span><span class="sxs-lookup"><span data-stu-id="d163d-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="d163d-115">Ce SBC particulier peut rencontrer des difficultés à se connecter à l’appelé, peut-être en raison d’un problème de configuration du réseau ou d’une autre erreur.</span><span class="sxs-lookup"><span data-stu-id="d163d-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="d163d-116">Néanmoins, il existe une plus grande colonie dans l’itinéraire qui peut être en mesure de joindre l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d163d-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="d163d-117">Dans le diagramme suivant, lorsqu’un utilisateur effectue un appel vers un numéro de téléphone, il y a deux éléments SBCs dans l’itinéraire qui peut éventuellement répondre à cet appel.</span><span class="sxs-lookup"><span data-stu-id="d163d-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="d163d-118">Au départ, SBC1.contoso.com est sélectionné pour l’appel, mais SBC1.contoso.com ne peut pas accéder à un réseau PTSN en raison d’un problème de réseau.</span><span class="sxs-lookup"><span data-stu-id="d163d-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="d163d-119">Par défaut, l’appel est effectué pour le moment.</span><span class="sxs-lookup"><span data-stu-id="d163d-119">By default, the call will be completed at this moment.</span></span> 
 
![Affichage de SBC impossible d’atteindre le RTC en raison d’un problème de réseau](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="d163d-121">Mais il existe une plus grande SBC dans l’itinéraire, qui peut éventuellement répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="d163d-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="d163d-122">Si vous configurez `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`le paramètre, le second SBC sera essayé--SBC2.contoso.com dans le schéma suivant:</span><span class="sxs-lookup"><span data-stu-id="d163d-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Affiche le routage sur le second SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="d163d-124">Le fait de définir le paramètre-FailoverResponseCodes et de spécifier les codes vous permet d’optimiser le routage et d’éviter les problèmes potentiels lorsqu’un SBC ne peut pas faire un appel en raison de problèmes réseau ou d’autres problèmes.</span><span class="sxs-lookup"><span data-stu-id="d163d-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="d163d-125">Valeurs par défaut: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="d163d-125">Default values:  408, 503, 504</span></span>

