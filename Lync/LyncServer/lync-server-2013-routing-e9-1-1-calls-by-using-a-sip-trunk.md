---
title: 'Lync Server 2013 : routage des appels E9-1-1 à l’aide d’une jonction SIP'
description: 'Lync Server 2013 : routage des appels E9-1-1 à l’aide d’une jonction SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e45b2b3d33556a5ff97235345c7b538023a7449
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571820"
---
# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="88192-103">Routage des appels E9-1-1 à l’aide d’une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88192-103">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88192-104">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="88192-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="88192-105">L’utilisation d’une jonction SIP pour se connecter à un fournisseur de services E9-1-1 certifié est une façon de déployer le système E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="88192-105">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="88192-106">Pour plus d’informations sur l’utilisation d’une passerelle ELIN pour se connecter à un fournisseur de services E9-1-1 PSTN (réseau téléphonique commuté), reportez-vous à la rubrique [appels de routage E9-1-1 à l’aide d’une passerelle Elin dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="88192-106">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="88192-107">Le diagramme suivant montre comment un appel d’urgence est acheminé de Lync Server vers le point de contrôle de la sécurité publique (PSAPI) lorsque vous utilisez une jonction SIP et un fournisseur de services E9-1-1 qualifié.</span><span class="sxs-lookup"><span data-stu-id="88192-107">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="88192-108">**Routage des appels E9-1-1 via une jonction SIP**</span><span class="sxs-lookup"><span data-stu-id="88192-108">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="88192-109">![Routage des appels d’urgence de Lync Server vers PSAPI](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Routage des appels d’urgence de Lync Server vers PSAPI")</span><span class="sxs-lookup"><span data-stu-id="88192-109">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="88192-110">Lorsqu’un appel d’urgence est passé à partir d’un client Lync Server compatible :</span><span class="sxs-lookup"><span data-stu-id="88192-110">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="88192-111">Une INVITE SIP qui contient l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultatif) et le numéro de rappel de conférence est acheminée vers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88192-111">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="88192-112">Lync Server établit une correspondance avec le numéro d’urgence et route l’appel (en fonction de la valeur d' **utilisation PSTN** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation, et à partir de là, via une jonction SIP vers le fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="88192-112">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="88192-p102">Le fournisseur de services E9-1-1 transfère l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclus un emplacement d’intervention d’urgence avec l’appel d’urgence, le fournisseur achemine automatiquement l’appel vers le centre d’appels de la sécurité publique approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre d’intervention en cas d’appels d’urgence (ECRC) vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant d’acheminer l’appel d’urgence au centre d’appels de la sécurité publique.</span><span class="sxs-lookup"><span data-stu-id="88192-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="88192-116">Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Lync.</span><span class="sxs-lookup"><span data-stu-id="88192-116">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="88192-117">Ce message apparaît toujours sur leur écran et il contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de rapidement répondre à l’appel d’urgence par un message instantané ou vocal.</span><span class="sxs-lookup"><span data-stu-id="88192-117">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="88192-118">Si vous avez configuré la stratégie d’emplacement pour les conférences et qu’elle est prise en charge par le fournisseur de services E9-1-1, un service de sécurité interne est intégré à l’appel avec des données audio unidirectionnelles ou bidirectionnelles.</span><span class="sxs-lookup"><span data-stu-id="88192-118">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="88192-119">Si l’appel est interrompu prématurément, le centre d’appels de la sécurité publique utilise le numéro de rappel pour contacter l’appelant directement.</span><span class="sxs-lookup"><span data-stu-id="88192-119">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

