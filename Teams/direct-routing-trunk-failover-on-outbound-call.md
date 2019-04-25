---
title: Basculement de jonction sur les appels sortants
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
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
description: Lisez cette rubrique pour savoir comment gérer les basculements de jonction pour les appels sortants à partir des équipes pour le contrôleur de Session en périphérie (SBC).
ms.openlocfilehash: b2da454097fcb0f0af91aefad987d195e9e0f912
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298555"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="8f751-103">Basculement de jonction sur les appels sortants</span><span class="sxs-lookup"><span data-stu-id="8f751-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="8f751-104">Cette rubrique explique comment éviter les basculements de jonction pour les appels sortants--des équipes pour le contrôleur de Session en périphérie (SBC).</span><span class="sxs-lookup"><span data-stu-id="8f751-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="8f751-105">Basculement sur les erreurs de réseau</span><span class="sxs-lookup"><span data-stu-id="8f751-105">Failover on network errors</span></span>

<span data-ttu-id="8f751-106">Si une jonction ne peut pas être connectée pour une raison quelconque, la connexion à la jonction même tentative sera effectuée à partir d’une autre Microsoft Datacenter.</span><span class="sxs-lookup"><span data-stu-id="8f751-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="8f751-107">Une jonction ne pas être connectée, par exemple, si une connexion est refusée, s’il existe un délai d’attente TLS ou s’il existe des problèmes de niveau réseau.</span><span class="sxs-lookup"><span data-stu-id="8f751-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="8f751-108">Par exemple, une connexion peut échouer si une limite l’accès administrateur pour le contrôleur SBC, uniquement à partir des adresses IP connues, mais oublie placer les adresses IP de tous les centres de données de routage Direct Microsoft sur la liste de contrôle d’accès (ACL) de la SBC.</span><span class="sxs-lookup"><span data-stu-id="8f751-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="8f751-109">Basculement de codes SIP spécifiques reçu à partir du contrôleur de Session en périphérie (SBC)</span><span class="sxs-lookup"><span data-stu-id="8f751-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="8f751-110">Si le routage Direct reçoit les codes d’erreur 4xx ou 6xx SIP en réponse à une invitation sortante, l’appel est considérée comme terminée par défaut.</span><span class="sxs-lookup"><span data-stu-id="8f751-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="8f751-111">Sortant signifie qu’un appel à partir d’un client équipes pour le Public téléphone réseau commuté (RTC) avec le flux de trafic suivants : Client équipes-> routage Direct-> SBC-réseau de téléphonie >.</span><span class="sxs-lookup"><span data-stu-id="8f751-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="8f751-112">Vous trouverez la liste des Codes SIP dans le [Protocole SIP (Session Initiation) RFC](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="8f751-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="8f751-113">Supposent une situation où un contrôleur SBC une réponse sur une invitation entrante par le code « expiration de délai 408 demande : le serveur ne peut pas fournir une réponse au sein d’une durée appropriée, par exemple, si elle a pas pu déterminer l’emplacement de l’utilisateur dans le temps.</span><span class="sxs-lookup"><span data-stu-id="8f751-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="8f751-114">Le client peut répéter de la demande sans modifications ultérieurement. »</span><span class="sxs-lookup"><span data-stu-id="8f751-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="8f751-115">Cette SBC spécifique peut être confronté à des difficultés pour connecter à l’appelé, par exemple en raison d’une configuration réseau incorrecte ou une autre erreur.</span><span class="sxs-lookup"><span data-stu-id="8f751-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="8f751-116">Toutefois, un SBC plus est dans l’itinéraire peut être en mesure d’atteindre l’appelé.</span><span class="sxs-lookup"><span data-stu-id="8f751-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="8f751-117">Dans le diagramme suivant, lorsqu’un utilisateur effectue un appel vers un numéro de téléphone, il existe deux SBCs dans l’itinéraire que peut transmettre potentiellement cet appel.</span><span class="sxs-lookup"><span data-stu-id="8f751-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="8f751-118">À l’origine, SBC1.contoso.com est activée pour l’appel, mais SBC1.contoso.com n’est pas en mesure d’atteindre un réseau PTSN en raison d’un problème de réseau.</span><span class="sxs-lookup"><span data-stu-id="8f751-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="8f751-119">Par défaut, l’appel réussira pour l’instant.</span><span class="sxs-lookup"><span data-stu-id="8f751-119">By default, the call will be completed at this moment.</span></span> 
 
![Montre SBC Impossible d’atteindre PSTN en raison de problèmes de réseau](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="8f751-121">Mais il existe un SBC plus dans l’itinéraire potentiellement capable de fournir l’appel.</span><span class="sxs-lookup"><span data-stu-id="8f751-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="8f751-122">Si vous configurez le paramètre `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, la deuxième SBC sera tenté--SBC2.contoso.com dans le diagramme suivant :</span><span class="sxs-lookup"><span data-stu-id="8f751-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Indique le routage vers le deuxième SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="8f751-124">Le paramètre - FailoverResponseCodes et en spécifiant les codes vous aide à bien paramétrer votre routage et éviter les éventuels problèmes lors d’un contrôleur SBC ne peut pas émettre un appel en raison de réseau ou d’autres problèmes.</span><span class="sxs-lookup"><span data-stu-id="8f751-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="8f751-125">Valeurs par défaut : 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="8f751-125">Default values:  408, 503, 504</span></span>

