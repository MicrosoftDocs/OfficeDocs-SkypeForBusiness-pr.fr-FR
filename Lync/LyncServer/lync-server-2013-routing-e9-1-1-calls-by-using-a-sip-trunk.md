---
title: 'Lync Server 2013 : routage des appels E9-1-1 à l’aide d’une jonction SIP'
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
ms.openlocfilehash: f45bd91eade0de6f290fd87e52effb25c669999a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Routage des appels E9-1-1 à l’aide d’une jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-29_

L’utilisation d’une jonction SIP pour se connecter à un fournisseur de services E9-1-1 certifié est une façon de déployer le système E9-1-1. Pour plus d’informations sur l’utilisation d’une passerelle ELIN pour se connecter à un fournisseur de services E9-1-1 PSTN (réseau téléphonique commuté), reportez-vous à la rubrique [appels de routage E9-1-1 à l’aide d’une passerelle Elin dans Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Le diagramme suivant montre comment un appel d’urgence est acheminé de Lync Server vers le point de contrôle de la sécurité publique (PSAPI) lorsque vous utilisez une jonction SIP et un fournisseur de services E9-1-1 qualifié.

**Routage des appels E9-1-1 via une jonction SIP**

![Routage des appels d’urgence de Lync Server vers PSAPI](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Routage des appels d’urgence de Lync Server vers PSAPI")

Lorsqu’un appel d’urgence est passé à partir d’un client Lync Server compatible :

1.  Une INVITE SIP qui contient l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultatif) et le numéro de rappel de conférence est acheminée vers Lync Server.

2.  Lync Server établit une correspondance avec le numéro d’urgence et route l’appel (en fonction de la valeur d' **utilisation PSTN** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation, et à partir de là, via une jonction SIP vers le fournisseur de services E9-1-1.

3.  Le fournisseur de services E9-1-1 transfère l’appel d’urgence vers le centre téléphonique de sécurité publique (PSAP) adéquat en fonction de l’emplacement fourni avec l’appel. Lorsque le client inclus un emplacement d’intervention d’urgence avec l’appel d’urgence, le fournisseur achemine automatiquement l’appel vers le centre d’appels de la sécurité publique approprié. Si l’emplacement a été entré manuellement par l’utilisateur, le centre d’intervention en cas d’appels d’urgence (ECRC) vérifie d’abord verbalement la précision de l’emplacement auprès de l’appelant avant d’acheminer l’appel d’urgence au centre d’appels de la sécurité publique.

4.  Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Lync. Ce message apparaît toujours sur leur écran et il contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de rapidement répondre à l’appel d’urgence par un message instantané ou vocal.

5.  Si vous avez configuré la stratégie d’emplacement pour les conférences et qu’elle est prise en charge par le fournisseur de services E9-1-1, un service de sécurité interne est intégré à l’appel avec des données audio unidirectionnelles ou bidirectionnelles.

6.  Si l’appel est interrompu prématurément, le centre d’appels de la sécurité publique utilise le numéro de rappel pour contacter l’appelant directement.

</div>

<span> </span>

</div>

</div>

</div>

