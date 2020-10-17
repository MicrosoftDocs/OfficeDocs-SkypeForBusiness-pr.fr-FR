---
title: 'Lync Server 2013 : routage des appels E9-1-1 à l’aide d’une passerelle ELIN'
description: 'Lync Server 2013 : routage des appels E9-1-1 à l’aide d’une passerelle ELIN.'
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
ms.openlocfilehash: f9ddbdbbdf10f9eecbffecaaf8416718bbdcf224
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545100"
---
# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Routage des appels E9-1-1 à l’aide d’une passerelle ELIN dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-05_

Certains partenaires dans le programme d’interopérabilité ouverte des communications unifiées fournissent des passerelles ELIN (Emergency Location Identification Number) certifiées, qui peuvent servir d’alternative à une connexion de jonction SIP à un fournisseur de services E9-1-1 certifié. Les passerelles ELIN prennent en charge la connectivité RNIS ou CAMA (Centralized Automatic Message Accounting) aux services E9-1-1 basé sur le réseau téléphonique commuté (RTC). Pour plus d’informations sur les partenaires qui fournissent des passerelles ELIN et des liens vers leurs documents, reportez-vous à [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425) .

Comme les connexions de jonction SIP aux fournisseurs de services E9-1-1, les passerelles ELIN permettent également de router un appel d’urgence vers le point de réponse publique (PSAPI) le plus approprié de l’appelant, mais ces passerelles utilisent un ELIN comme identificateur d’emplacement. Vous définissez numéros pour chaque lieu de réponse d’urgence (ERL) de votre organisation (pour plus d’informations, consultez la rubrique [Managing locations for Elin Gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Lorsque vous utilisez une passerelle ELIN pour les appels d’urgence, vous utilisez la même infrastructure Lync Server E9-1-1 que vous utiliserez pour une connexion de jonction SIP. Autrement dit, la base de données du service informations d’emplacement fournit l’emplacement au client Lync Server, et la stratégie d’emplacement active la fonctionnalité et définit le routage. Toutefois, avec une passerelle ELIN, vous devez ajouter le numéros à la base de données du service informations d’emplacement et faire en sorte que votre opérateur RTC les télécharge dans la base de données ALI (Automatic location identification).

Lorsqu’un client Lync obtient son emplacement à partir du service d’informations d’emplacement, l’emplacement inclut le ELIN. Pendant un appel d’urgence, le ELIN est inclus avec l’emplacement envoyé à la passerelle ELIN. La passerelle ELIN identifie l’appel comme un appel d’urgence et permute le numéro de l’appelant avec le ELIN. La passerelle ELIN achemine ensuite l’appel vers le RTC avec le ELIN comme numéro d’appel. Le fournisseur PSTN E9-1-1 recherche le ELIN dans la base de données ALI, qui est une base de données associée à la base de données de guide des adresses principales (MSAG). Le RTC envoie ensuite l’appel au site PSAPI le plus approprié en fonction de la recherche ALI, et le PSAPI envoie d’abord des répondeurs à l’emplacement de l’appelant en fonction de la recherche ALI. Le numéro d’appel est mis en cache sur la passerelle ELIN pour une durée prédéfinie pour les rappels. Au cours d’un rappel, le PSAPI atteint la passerelle ELIN, qui permute le ELIN pour le numéro DID (direct Inward dialing) de l’appelant.

Les passerelles ELIN prennent en charge les appels d’urgence provenant uniquement du réseau de votre organisation. Elles ne prennent pas en charge ceux passés en dehors de votre réseau.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation d’une connexion de jonction SIP pour les appels d’urgence, voir <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">routage des appels E9-1-1 à l’aide d’une jonction SIP dans Lync Server 2013</A>.



</div>

Le diagramme suivant montre comment un appel d’urgence est acheminé de Lync Server vers PSAPI lorsque vous utilisez une passerelle ELIN.

**Routage des appels E9-1-1 vers une passerelle ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Une INVITE SIP INVITE contenant l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultatif) et le numéro de rappel de conférence est acheminée vers Lync Server.

2.  Lync Server correspond au numéro d’urgence, puis achemine l’appel (en fonction de la valeur d' **utilisation PSTN** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation et de là, vers une passerelle Elin.

3.  La passerelle ELIN achemine l’appel via une jonction RNIS ou CAMA vers le réseau téléphonique commuté.

4.  Le réseau téléphonique commuté identifie l’appel comme un appel d’urgence et l’achemine vers un routeur sélectif E9-1-1 du réseau. Le routeur sélectif E9-1-1 recherche le numéro de l’appelant dans la base de données ALI afin d’obtenir l’emplacement géographique correspondant. Le routeur sélectif E9-1-1 envoie l’appel au centre PSAP le plus approprié en fonction des informations d’emplacement récupérées à partir de la base de données ALI.

5.  Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Lync. Ce message apparaît toujours sur leur écran et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de répondre rapidement à l’appel d’urgence par un message instantané ou vocal.

6.  Si l’appel est interrompu prématurément, le centre d’appels de la sécurité publique utilise le numéro d’identification de l’emplacement en cas d’urgence pour contacter l’appelant directement. La passerelle ELIN remplace le numéro d’identification de l’emplacement en cas d’urgence par le numéro SDA (sélection directe à l’arrivée).

</div>

<span> </span>

</div>

</div>

</div>

