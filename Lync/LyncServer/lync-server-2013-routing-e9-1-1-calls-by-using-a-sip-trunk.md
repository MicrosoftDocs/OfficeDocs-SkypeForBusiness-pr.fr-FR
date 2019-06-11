---
title: 'Lync Server 2013 : Routage des appels E9-1-1 avec une jonction SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c537b66883ab786bc28e3cc808874c0fcb79b92d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Routage des appels E9-1-1 avec une jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-29_

Se connecter à un fournisseur de services E9-1-1 éligible à l’aide d’une jonction SIP vous permet de déployer E9-1-1. Pour plus d’informations sur l’utilisation d’une passerelle ELIN pour se connecter à un fournisseur de services RTC (réseau téléphonique commuté) E9-1-1, voir [routage des appels E9-1-1 à l’aide d’une passerelle Elin dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Le diagramme suivant illustre la manière dont un appel d’urgence est acheminé de Lync Server vers le point d’accès public sécurisé (PSAPI) lorsque vous utilisez une ligne SIP et un fournisseur de services E9-1-1 éligible.

**Routage des appels E9-1-1 via une jonction SIP**

![Routage des appels d’urgence de Lync Server vers PSAPI] (images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Routage des appels d’urgence de Lync Server vers PSAPI")

Lorsqu’un appel d’urgence est passé à partir d’un client compatible Lync Server, procédez comme suit:

1.  Une invitation SIP qui contient l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultative) et le numéro de rappel de conférence sont routés vers Lync Server.

2.  Lync Server correspond au numéro d’urgence et route l’appel (en fonction de la valeur d' **utilisation RTC** définie dans la stratégie d’emplacement applicable) sur un serveur de médiation et à partir de là, sur une ligne SIP pour le prestataire de services E9-1-1.

3.  Le fournisseur de services E9-1-1 route l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclut un emplacement de situation d’urgence (ERL) validé dans l’appel d’urgence, le fournisseur route automatiquement l’appel vers le PSAP approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre de réponse aux appels d’urgence vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant de router l’appel d’urgence vers le PSAP.

4.  Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs des responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Lync. Ce message s’affiche toujours sur leur écran et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de répondre rapidement à l’appel d’urgence par un message instantané ou vocal.

5.  Si vous avez configuré la stratégie d’emplacement pour les conférences et qu’elle est prise en charge par le fournisseur de services E9-1-1, un service de sécurité interne est intégré à l’appel avec des données audio unidirectionnelles ou bidirectionnelles.

6.  Si l’appel se termine prématurément, le PSAP utilise le numéro de rappel pour contacter directement l’appelant.

</div>

<span> </span>

</div>

</div>

</div>

