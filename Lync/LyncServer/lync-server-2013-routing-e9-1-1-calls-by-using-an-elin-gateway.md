---
title: 'Lync Server 2013 : Routage des appels E9-1-1 via une passerelle ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Routage des appels E9-1-1 via une passerelle ELIN dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-05_

Certains partenaires du programme Unified Communications Open Interoperability fournissent des passerelles compatibles avec les numéros ELIN (Emergency Location Identification Number), ce qui peut servir de solution de remplacement pour une connexion de jonction SIP à un fournisseur de services E9-1-1 qualifié. Les passerelles ELIN prennent en charge la connectivité RNIS (réseau numérique à intégration de services) ou CAMA (Centralized Automatic Message Accounting) aux services E9-1-1 basés sur un réseau téléphonique commuté. Pour plus d’informations sur les partenaires qui fournissent des passerelles ELIN et des liens [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)vers leurs documents, voir.

Comme pour les connexions SIP Trunk à des fournisseurs de services E9-1-1, les passerelles ELIN fournissent également le moyen de diriger un appel d’urgence vers le point d’accès de l’appelant le plus approprié (PSAPI), mais ces passerelles utilisent un ELIN en tant qu’identificateur d’emplacement. Pour plus d’informations, reportez-vous à la section [gestion des emplacements des passerelles Elin dans Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md).

Lorsque vous utilisez une passerelle ELIN pour les appels d’urgence, vous utilisez la même infrastructure Lync Server E9-1-1 que vous utiliseriez pour une connexion SIP Trunk. Autrement dit, la base de données de service des informations d’emplacement spécifie l’emplacement du client Lync Server et la stratégie d’emplacement active la fonctionnalité et définit le routage. Toutefois, avec une passerelle ELIN, vous devez ajouter le ELINs à la base de données de service des informations d’emplacement et faire en sorte que votre opérateur PSTN les charge dans la base de données d’identification d’emplacement automatique (ALI).

Lorsqu’un client Lync obtient son emplacement auprès du service d’information d’emplacement, l’emplacement inclut ELIN. Au cours d’un appel d’urgence, le ELIN est inclus avec l’emplacement envoyé à la passerelle ELIN. La passerelle ELIN identifie l’appel en tant qu’appel d’urgence et permute le numéro de l’appelant par le ELIN. La passerelle ELIN route ensuite l’appel vers le RTC avec le ELIN comme numéro d’appel. Le fournisseur RTC E9-1-1 recherche ELIN dans la base de données ALI, qui est une base de données associée à la base de données du Guide de l’adresse principale (MSAG). Le RTC envoie alors l’appel vers le site PSAPI le plus approprié en fonction de la recherche ALI, et le champ PSAPI envoie les premiers répondants à l’emplacement de l’appelant en fonction de la recherche ALI. Le numéro d’appel est mis en cache sur la passerelle ELIN pour une durée prédéfinie pour les rappels. Au cours d’un rappel, le PSAPI atteint la passerelle ELIN, qui permute le ELIN pour le numéro de numérotation direct de l’appelant.

Les passerelles ELIN prennent en charge les appels d’urgence effectués au sein du réseau de votre organisation. Elles ne prennent pas en charge les appels d’urgence effectués hors de votre réseau.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation d’une connexion SIP Trunk pour les appels d’urgence, reportez-vous <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">à la section routage des appels E9-1-1 en utilisant un Trunk SIP dans Lync Server 2013</A>.



</div>

Le diagramme suivant montre comment un appel d’urgence est acheminé de Lync Server vers le PSAPI lorsque vous utilisez une passerelle ELIN.

**Acheminement d’appels E9-1-1 avec une passerelle ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Une invitation SIP contenant l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultative) et le numéro de rappel de conférence sont routés vers Lync Server.

2.  Lync Server correspond au numéro d’urgence, puis route l’appel (en fonction de la valeur d' **utilisation RTC** définie dans la stratégie d’emplacement applicable) sur un serveur de médiation, et de là à une passerelle Elin.

3.  La passerelle ELIN achemine l’appel via une jonction RNIS ou CAMA vers le réseau téléphonique commuté.

4.  Le réseau téléphonique commuté identifie l’appel comme un appel d’urgence et l’achemine vers un routeur sélectif E9-1-1 du réseau. Le routeur sélectif E9-1-1 recherche le numéro de l’appelant dans la base de données ALI afin d’obtenir l’emplacement géographique correspondant. Le routeur sélectif E9-1-1 envoie l’appel au centre PSAP le plus approprié en fonction des informations d’emplacement récupérées à partir de la base de données ALI. 

5.  Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs des responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Lync. Ce message s’affiche toujours sur leur écran et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de répondre rapidement à l’appel d’urgence par un message instantané ou vocal.

6.  Si l’appel est interrompu prématurément, le centre PSAP utilise le numéro ELIN pour contacter directement l’appelant. La passerelle ELIN remplace le numéro ELIN par le numéro direct de l’appelant.

</div>

<span> </span>

</div>

</div>

</div>

