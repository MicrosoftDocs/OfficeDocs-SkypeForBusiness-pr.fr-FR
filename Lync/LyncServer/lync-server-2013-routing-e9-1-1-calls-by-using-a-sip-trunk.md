---
title: 'Lync Server 2013 : Routage des appels E9-1-1 avec une jonction SIP'
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
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="fd58c-102">Routage des appels E9-1-1 avec une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd58c-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd58c-103">_**Dernière modification de la rubrique :** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="fd58c-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="fd58c-104">Se connecter à un fournisseur de services E9-1-1 éligible à l’aide d’une jonction SIP vous permet de déployer E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="fd58c-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="fd58c-105">Pour plus d’informations sur l’utilisation d’une passerelle ELIN pour se connecter à un fournisseur de services RTC (réseau téléphonique commuté) E9-1-1, voir [routage des appels E9-1-1 à l’aide d’une passerelle Elin dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="fd58c-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="fd58c-106">Le diagramme suivant illustre la manière dont un appel d’urgence est acheminé de Lync Server vers le point d’accès public sécurisé (PSAPI) lorsque vous utilisez une ligne SIP et un fournisseur de services E9-1-1 éligible.</span><span class="sxs-lookup"><span data-stu-id="fd58c-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="fd58c-107">**Routage des appels E9-1-1 via une jonction SIP**</span><span class="sxs-lookup"><span data-stu-id="fd58c-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="fd58c-108">![Routage d’appel d’urgence de Lync Server vers PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Routage d’appel d’urgence de Lync Server vers PSAP")</span><span class="sxs-lookup"><span data-stu-id="fd58c-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="fd58c-109">Lorsqu’un appel d’urgence est passé à partir d’un client compatible Lync Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fd58c-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="fd58c-110">Une invitation SIP qui contient l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultative) et le numéro de rappel de conférence sont routés vers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fd58c-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="fd58c-111">Lync Server correspond au numéro d’urgence et route l’appel (en fonction de la valeur d' **utilisation RTC** définie dans la stratégie d’emplacement applicable) sur un serveur de médiation et à partir de là, sur une ligne SIP pour le prestataire de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="fd58c-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="fd58c-p102">Le fournisseur de services E9-1-1 route l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclut un emplacement de situation d’urgence (ERL) validé dans l’appel d’urgence, le fournisseur route automatiquement l’appel vers le PSAP approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre de réponse aux appels d’urgence vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant de router l’appel d’urgence vers le PSAP.</span><span class="sxs-lookup"><span data-stu-id="fd58c-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="fd58c-115">Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs des responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Lync.</span><span class="sxs-lookup"><span data-stu-id="fd58c-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="fd58c-116">Ce message s’affiche toujours sur leur écran et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de répondre rapidement à l’appel d’urgence par un message instantané ou vocal.</span><span class="sxs-lookup"><span data-stu-id="fd58c-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="fd58c-117">Si vous avez configuré la stratégie d’emplacement pour les conférences et qu’elle est prise en charge par le fournisseur de services E9-1-1, un service de sécurité interne est intégré à l’appel avec des données audio unidirectionnelles ou bidirectionnelles.</span><span class="sxs-lookup"><span data-stu-id="fd58c-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="fd58c-118">Si l’appel se termine prématurément, le PSAP utilise le numéro de rappel pour contacter directement l’appelant.</span><span class="sxs-lookup"><span data-stu-id="fd58c-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

